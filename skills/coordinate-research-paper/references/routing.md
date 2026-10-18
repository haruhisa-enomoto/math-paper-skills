# Routing workers

This file owns how the coordinator starts, resumes, and checks each worker.
Host-specific paths, build commands, and diagnostics come from the host
overlay. Verify each command form once on the host before relying on it, and
record the verified form in the state file.

## General rules

- Run long worker commands as tracked background tasks of the coordinator's
  harness, so that completion is reported. Never detach a worker with
  `nohup`, `&`, `disown`, or `setsid`.
- Use subscription logins, not API keys. Before the first call, check that
  no API-key environment variable (for example `OPENAI_API_KEY`) is set for
  the worker; unset it for the call if it is.
- Keep worker prompts short and factual: what arrived, what to do, which
  skill to load, what to return. Do not add diagnoses, expectations, or
  opinions about the manuscript.
- Capture each worker's session identity on its first call and resume it
  for later turns of the same role.
- Save every worker's final message to a file in the review directory and
  read it from there.
- Pin the model and effort on every call, as in the commands below, so that
  a changed tool default cannot switch a worker silently. Record the pinned
  values in the state file. The reader subagents get theirs from their agent
  definitions.

## Pinned models

| Role | Model | Effort | How it is pinned |
|---|---|---|---|
| Writer, auditor | `gpt-6-astra` | high | `-m gpt-6-astra -c model_reasoning_effort="high"` |
| Polisher | `gemini-4-argon-high` | high (in the model ID) | `--model gemini-4-argon-high`; do not add `--effort` |
| FR, SE | Claude Opus | medium | agent definition front matter |
| Plain reader | Claude Opus | session default | fresh subagent |

Keep the readers at medium effort. A reader at higher effort tends to fill
gaps itself and report nothing, which defeats the review.

## Writer (Codex)

First call in a new session, capturing the session identity from the first
JSON event (`{"type":"thread.started","thread_id":...}`):

```sh
codex exec -C <repo> -s workspace-write -m gpt-6-astra \
  -c model_reasoning_effort="high" \
  -c 'sandbox_workspace_write.writable_roots=["<repo>/.git"]' \
  --json -o <review-dir>/writer-<n>.md "<prompt>" </dev/null
```

Later turns:

```sh
codex exec resume <writer-session-id> -m gpt-6-astra \
  -c model_reasoning_effort="high" -c sandbox_mode="workspace-write" \
  -c 'sandbox_workspace_write.writable_roots=["<repo>/.git"]' \
  -o <review-dir>/writer-<n>.md "<prompt>" </dev/null
```

`codex exec resume` takes no `-s` flag; without `-c sandbox_mode=...` a
resumed turn falls back to the sandbox in the user's Codex config, which may
be full access. The `workspace-write` sandbox mounts `.git` read-only, so
without the writable root the writer cannot create its checkpoint.
`</dev/null` stops Codex from waiting for extra input on stdin.

Self-audit prompt (after a new draft or structural change, before its first
review, and before polish):

```text
Load write-research-paper and do the writer self-audit of <manuscript path>
at <revision>: read it in order against every item of the paper-writing
checklist, repair what fails, and record the pass in the writing state.
Relay rule: do not launch reviews. Compile, run the host diagnostics, create
the host checkpoint, and end with the new revision and the failed items.
```

Discussion mode, when the owner wants to talk with the writer before any
edit: resume the writer with `-c sandbox_mode="read-only"` and

```text
Owner direction (verbatim):
<owner message>

Relay rule: discussion only; do not edit. Reply with your understanding, your
plan, and your questions.
```

Relay the reply to the owner unchanged, and the owner's answer back, until
the owner says to proceed.

Plan prompt for a new paper (Phase 0):

```text
Load write-research-paper. We will write a new paper: <owner's description,
verbatim>. Catch up on the relevant results and sources in the repository.
Do not draft yet. Propose a plan: audience and background, paper promise,
main theorems, section jobs, what to include and leave out, and authorship.
Ask any question whose answer would change the plan.
```

Draft prompt after G0:

```text
Owner reply to your plan: <verbatim>. Draft the manuscript according to the
agreed plan. Do not launch reviews. Compile, run the host diagnostics,
create the host checkpoint, and end with the new revision and the
manuscript path.
```

Revision prompt after a review round:

```text
Round <k>. Reviews of revision <reviewed revision> of <manuscript path>
arrived: <report paths>. Load write-research-paper and revise the manuscript
based on these reviews, using the paper's writing state and revision batch.

Coordinator ledger tags (relay record, not owner direction):
<tag lines, or "none">

Owner direction (verbatim):
<owner comments, or "none">

Owner direction context (coordinator):
<the question or gate the owner was answering, or "none">

Relay rule: do not launch reviews; the coordinator runs them. Compile, run
the host diagnostics, create the host checkpoint, and end with the new
revision, the revision-batch path, and any item you defer or mark as owner
judgment.
```

Keep the labels exactly. Only text under "Owner direction (verbatim)" comes
from the owner; the context line, ledger tags, and relay rules are the
coordinator's, and the writer must not cite them as owner decisions.

## FR and SE readers (Claude subagents)

Use fresh subagents with no inherited conversation (in Claude Code, the
`paper-first-reader` and `paper-skeptical-editor` agent types where the host
defines them; never a fork). Follow the write skill's launchers exactly:
freeze the reading copy, fill the directions, initialize FR, issue its
segments one at a time with the fixed messages, and continue the same FR
subagent for every segment and the synthesis. Launch SE with its single
packet. Run FR and SE in parallel. The launchers and directions are
[FR direction](../../write-research-paper/assets/first-reader-direction.md),
[FR launcher](../../write-research-paper/assets/first-reader-launcher.md),
[SE direction](../../write-research-paper/assets/skeptical-editor-direction.md),
and [SE launcher](../../write-research-paper/assets/skeptical-editor-launcher.md).

Use supervisor-persisted delivery for FR and SE in Claude Code: the reader
returns its report text and the coordinator saves it verbatim. Claude Code
refuses report-file writes from subagents ("Subagents should return findings
as text, not write report files") even when the agent has a Write tool, so a
Write tool is no basis for reader-persisted delivery. This costs coordinator
context, since every FR segment report passes through the coordinator.

The coordinator has read the manuscript and the history, so it is
contaminated: it checks process only, and its messages to readers stay
uniform.

Known harness leak: Claude Code may give a reader subagent a git-status
snapshot with recent commit subjects. It reveals that earlier rounds
existed, not their findings. Record it if a reader reports it; it does not
by itself invalidate the run.

## Plain reader

A fresh agent with no skills, no direction file, no repository docs, and no
history. Give it only the frozen TeX reading copy (or the compiled PDF) and
this prompt:

```text
Do not load any skills, repository documents, notes, or history. Read
<path> as a research mathematician reading a new preprint in this area.
Write your honest impressions: what is missing, unmotivated, odd,
repetitive, too detailed, or too compressed, and what works well. Free
form; cite locations.
```

Default worker: a fresh Claude Opus subagent. The owner may choose Argon via
`agy` instead; record the choice in the state file. Save the reply verbatim.

## Polisher (agy)

First call, capturing `conversation_id` from the JSON output. Put every flag
before `-p`; the argument after `-p` is the prompt.

```sh
agy --output-format json --model gemini-4-argon-high --mode accept-edits \
  -p "<prompt>" > <review-dir>/polish-<n>.json
```

Later turns: add `--conversation <id>` before `-p`. In `accept-edits` mode
agy edits files and also runs shell commands (build, git) without asking, so
it is not sandboxed; keep its prompts scoped to the manuscript. Stop if a
print-mode run waits for approval.

Rewrite prompt:

```text
Load polish-math-prose in rewrite mode. Polish <manuscript scope> with fresh
eyes. Do not read earlier review reports or revision batches. Locked owner
decisions: <list>. Owner-banned wording: <list>. Log every substantive
mathematical touch in REVISION-NOTES.md. Compile, run the host diagnostics,
create the host checkpoint, and end with the new revision.
```

Repair prompt:

```text
Audit report arrived: <path>. Load polish-math-prose in repair mode and
repair the findings marked as introduced by the polish. Compile, run the
host diagnostics, create the host checkpoint, and end with the new revision.
```

## Math auditor (Codex, read-only)

Diff audit after a polish or repair turn:

```sh
codex exec -C <repo> -s read-only -m gpt-6-astra \
  -c model_reasoning_effort="high" --json -o <review-dir>/audit-<n>.md \
  "<prompt>" </dev/null
```

```text
Audit the mathematics of the change from <pre-polish revision> to <current
revision> of <manuscript>, using git diff and REVISION-NOTES.md. Do not load
paper-writing skills; this is a math audit, not an exposition review. For
each defect give the locator, what is wrong, and whether the polish
introduced it or it predates the polish. End with exactly one line:
"Audit verdict: CLEAN" or "Audit verdict: DEFECTS".
```

Resume the same auditor session for re-audits within one polish phase, with
`-c sandbox_mode="read-only"` (resume ignores `-s`). The final audit uses a
new session and audits the whole manuscript, not a diff:

```text
Do a full math audit of <manuscript> at <revision>, TeX only. Do not load
paper-writing skills or read notes, reviews, or history. Check every
statement and proof step. For each numbered result give one line: the
result, what you checked, and any gap. Then end with exactly one line:
"Audit verdict: CLEAN" or "Audit verdict: DEFECTS".
```

A verdict without the per-result record is incomplete; ask the auditor for
the record before accepting it.

## Checking a returned step

- The revision changed as claimed, and the checkpoint exists.
- The build succeeded and the host diagnostics ran on the new revision.
- The edit stayed within scope (`git diff --stat` against the previous
  revision).
- For review reports: coverage, literal verdict, and isolation statements
  are present, as the reader protocols require.
