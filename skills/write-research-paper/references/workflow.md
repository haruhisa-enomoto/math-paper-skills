# Mathematics-paper workflow

This file owns writer routing, adjudication, and completion. The
[exposition standard](exposition-standard.md) owns reader-facing quality;
mode-specific reader protocols own review execution and report requirements.

## Authority and current state

Infer the target revision, requested outcome, edit scope, content and structural
locks, audience, owner-decision boundary, and finish state from conversation
and read-only inspection. A review or diagnosis alone does not authorize edits.
Carry settled positive choices forward; do not require their approval again.
Ask only when an unresolved choice would materially change audience, promise,
structure, theorem hierarchy, scope, voice, or length/detail boundary beyond
existing authority. Continue independent authorized work while awaiting it.

Treat owner wording as approved copy only when offered as copy. If the owner
recalls an earlier version or gives approximate wording, recover that text when
available; otherwise preserve the substantive direction and identify replacement
wording as new. Do not substitute a new voice or terminology decision silently.

For substantial work keep one compact writing state: revision, positive locks,
review verdicts and closure evidence, unresolved decisions, and next action.
Use the host's existing state or [template](../assets/writing-state.md).
A bounded task needs only the corresponding information, not a new state file.

## Route the task

Match the execution mode to the owner's request:

```text
writer/reviser turn: draft or adjudicate/revise from named reports -> compile + host diagnostics -> finish turn
review-supervisor turn: freeze manuscript -> run isolated FR and/or SE subagent relay -> synthesize report
full-cycle turn (when explicitly requested): draft/integrate -> FR/SE review -> adjudicate/revise -> optional delta regression -> validate/finish
post-convergence prose polish: hand off to $polish-math-prose (rewrite) -> mathematical diff audit <-> $polish-math-prose (repair)
```

In a multi-model workflow, the writer model (e.g. Codex or Claude) and the
review supervisor (e.g. Claude Opus) often run in separate turns or sessions.
Do not automatically launch `FR`, `SE`, or `Delta` subagents at the end of a
drafting or revision turn unless the owner asks you to run a review round or
full cycle. Conversely, when asked to supervise an `FR` or `SE` review round,
run the isolated reader protocol and return the completed report without
editing the manuscript unless also authorized to revise.

A named-section review receives the cumulative prefix through that section, but
edits remain confined to the authorized scope. Request a needed expansion once.
Adding a section includes the minimal introduction, transition, cross-reference,
and later-summary edits needed to integrate it.

For a new paper or material change of shape, establish audience, paper promise,
result hierarchy, section jobs, reading paths, main-text/appendix split, and
detail budget. Reuse settled choices. Offer a provisional title, front-matter
sketch, and representative passage when useful to resolve a remaining choice;
there are no predetermined approval batches. Reopen only materially changed
choices that are not already authorized.

## Draft, integrate, and review

Draft within the locks, integrate in reading order, and apply the shared
standard, including first encounters and a top-to-bottom boundary pass.
Record revision and scope; writer self-review is not independent evidence.

When supervising a review round, freeze the reading copy, preserving source
locators for flattened inputs. Supervise fresh isolated readers under their
mode-specific protocols. Continuous reading retains one reader and staged
cumulative exposure. Before manuscript exposure, choose the protocol's
reader-persisted or supervisor-persisted report delivery and align the direction
with host permissions. Both modes preserve the same reader-authored editorial
annotations and append-only history; do not improvise delivery after a failure.
Editorial reading accepts one packet with instructions and the complete frozen
paper. Withhold writer history, owner discussion, previous
reviews, vocabulary diagnostics, expected findings, proposed repairs, and
author's choices or review contracts other than the audience. If the required
isolation or continuity cannot be established, report the review invalid.

When running both continuous and editorial reviews in sequence, apply clear
local/objective repairs from the continuous reading first to create a coherent
candidate before running the editorial audit, or run them as directed by the
owner.

## Exhaustive adjudication

Before editing from a report, read it completely and populate
[revision-batch.md](../assets/revision-batch.md). Preserve each literal source
verdict and exact revision. Map every ranked finding, separately stated
objective burden, and actionable editorial inventory item to exactly one
repair cluster; assign source IDs where missing. Repeated instances may share
one cause and cluster, but none may disappear. Journal entries support findings
and need not each become a cluster.

For each cluster record the observed burden, success criterion, planned repair,
non-scope, risk, decision, and changed locators. Record the decision in two
parts, so that disagreeing with the reader's repair is never recorded as
disagreeing with the burden:

- **Burden**: `accepted`, `rejected`, or `deferred`. `rejected` needs exact
  manuscript text or an explicit audience/owner contract showing that the
  stated audience would not stall there; a reason about the reader's proposed
  repair never rejects the burden. `deferred` keeps an unresolved decision or
  missing evidence open.
- **Repair**, for an accepted burden: `reader's` (the reader's proposed
  repair) or `alternative` (move, inline, merge, rewrite, delete, or other).
  When a rule or owner direction bars the reader's repair, name it and choose
  an alternative.

An accepted burden must change text at its locator; if nothing changes,
record the burden as rejected with its evidence. Older records map as
`implement` = accepted with the reader's repair, `modify` = accepted with an
alternative, `reject` = rejected, and `defer` = deferred.

Do not erase a reported reading difficulty, backward search, translation to an
exact predicate, or cumulative loss of orientation merely because an expert can
recover the intended meaning. Preserve useful positive observations and
unresolved reader questions without automatically turning them into repair
clusters. Distinguish later manuscript clarification from an explicit correction
of a reader mistake. Disagreeing with proposed wording does not reject the
observation. A missing predicate or referent fixed by accepted mathematics is a
local/objective defect,
as are broken references, undefined notation, omitted accepted hypotheses,
literal errors, and direct process-leakage repairs. A nondefect decision needs
concrete text already available at that point or an explicit audience contract.

Paper promise, architecture, title/abstract voice, theorem hierarchy, literature
position, substantial retention, new terminology, and disputed diagnoses can
require owner judgment, as does any edit that changes the wording of a recorded
owner choice. Resolve them within existing authority where settled;
otherwise present the recommendation, reason, tradeoff, and minimal alternative.
Missing context warrants a conditional diagnosis, not an invented repair.

Avoid **structural bloat**: prefer deletion, reordering, or direct explanation
before adding a new numbered definition, remark, or auxiliary machinery. At the
**sentence and paragraph level**, however, never wedge compressed parenthetical
clauses, semicolon chains, or causative shortcuts (`"X makes Y"`, `"X puts Y"`)
into an existing sentence just to minimize diff lines. When a sentence or
paragraph needs repair, rewrite the affected sentence and its immediate
transitions so that the whole paragraph reads naturally and coherently in
reading order. After each repair, reread the enclosing section in reading order
(for the abstract or introduction, all of it) to verify natural flow. Do not
rewrite a passage that is already clear and natural merely because a reviewer
offers alternative phrasing.
For retained editorial material, record the role, loss under deletion, and
beneficiary; for precision findings, record exact referent or predicate, what
current wording licenses, and the reader's reconstruction burden.

## Host diagnostics and optional delta regression

After repairs, run every required host diagnostic over its required scope and
adjudicate every warning at the exact revision. Warnings are locations for
judgment, not automatic defects. For terminology, judge meaning, necessity,
and introduction before spelling or hyphenation. Never change text just to
clear a flag. Rerun after wording changes; withhold diagnostics from
independent readers. Host-specific commands and report conventions belong in
the host overlay.

When the owner requests bounded post-edit regression (or when running an
autonomous full-cycle loop), use the
[delta protocol](../../read-research-paper/references/delta-review.md):
changed regions, surrounding dependencies, cluster IDs, and neutral success
criteria without diagnoses or preferred wording. Compare the packet's covered
IDs with the revision batch before launch and with the returned report.
A delta closes only those accepted-burden clusters actually checked; it
cannot close omitted or deferred findings or certify unchanged text.

When the owner instead runs iterative `FR`/`SE` rounds or hands off to
`polish-math-prose` and a mathematical diff audit once `FR`/`SE` converge, do
not launch unsolicited delta subagents after local edits.

## Finish at one exact revision

Require current locks, complete source-finding coverage without duplicate or
orphan IDs, no unresolved objective finding, and no deferral unless the owner
explicitly excludes it. Preserve source `FAIL` verdicts; record current closure
separately rather than relabeling old reports.

Compile and inspect the log, complete all host diagnostics and artifact gates,
and inspect the aggregate diff. Render only affected pages for a concrete
visual concern, such as a diagram, clipping, or unusual break. Create the
host-authorized checkpoint only after required gates pass. Keep review reports
in temporary storage unless durable preservation is authorized. Do not invent
an edit or empty checkpoint when no repair is accepted. Submission packages,
release declarations, and external publication require separate authority.
