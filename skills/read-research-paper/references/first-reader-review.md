# Continuous first-reader review

Read this guide before running or supervising a first-reader review of a
manuscript.  It describes a relay protocol in which one reader reads a paper
in order, without ever seeing what comes later, and a supervisor issues the
paper to it one segment at a time.

This is a test of exposition, not of truth.  It answers: can a competent
reader who does not know the cited sources follow this paper on a first
pass?  It does not answer whether the mathematics is correct.  A proof audit
is a different task with a different protocol; do not merge them. It also
does not decide whether every understandable passage earns its space or
whether understandable wording exposes its exact mathematical interface. Use
[skeptical-editor protocol](skeptical-editor-review.md) for that independent
whole-manuscript test.

Reusable direction and launcher templates ship with the writer skill as
[first-reader direction](../../write-research-paper/assets/first-reader-direction.md)
and [first-reader launcher](../../write-research-paper/assets/first-reader-launcher.md).
The writing standards the review applies are in the
[shared exposition standard](../../write-research-paper/references/exposition-standard.md);
before receiving any manuscript text, the reader reads that guide completely
and applies it throughout the review.

## When to run one

- Before submission, once the mathematics is settled.
- After a substantial rewrite, to test whether the rewrite worked.
- When a paper leans heavily on imported results and you suspect the reader
  is being asked to trust rather than follow.

Do not run one on a manuscript still changing under you: the journal anchors
to line numbers and quoted phrases, and both drift.

## The core constraint

Forward-blindness: the reader must never use information from a later part
of the paper to excuse an earlier sentence.  This is the whole value of the
exercise.  An expert who has read the paper twice cannot tell you where a
first reader stumbles, because they no longer stumble there.

Two distinct threats, often confused.

- **Contamination** — the reader already knows the later material.  Solved
  by starting from a fresh agent with no prior context.
- **Read-ahead** — the reader looks forward during the review.  Solved by
  never giving it the later text.

Splitting the paper across several agents solves neither better than a
single reader does, and it costs you the findings that matter most.  Only a
continuous reader can report that a convention fixed on page 4 was
unusable on page 14, that a symbol now carries its third meaning, or that
the sentence which finally orients the reader arrives eight hundred lines
too late.  Use one reader.

If you want a second opinion, run a second *full-pass* reader on a different
model.  That samples who stumbles where, which is the axis worth sampling.
Do not split by section.

## Requirements for a valid run

A run is forward-blind only when all of the following hold.

1. **One fresh subagent is the reader.**  Spawn a new subagent with no
   inherited conversation turns or research context.  The supervisor must not
   read in the reader role.  When the harness offers context forking,
   explicitly choose no inherited context rather than trusting its default.
   In Codex, use `fork_turns: "none"`.  In Claude Code, use a fresh agent or
   session rather than a fork agent.  On another harness, use its equivalent
   no-inherited-context option.
2. **The same reader completes the run.**  Send every segment and the closing
   instruction to that same subagent.  Do not replace it between sections or
   spawn a new reader per segment.
3. **The reader is initialized before it sees any manuscript text.**  Send the
   guide-only initialization message first and wait for the reader to confirm
   readiness.  Do not combine initialization and the first segment in one
   message: the reader cannot reliably serialize the two tasks itself, and a
   reader that opens manuscript text before confirming readiness invalidates
   the run.
4. **Later text remains unavailable.**  Give the reader a cumulative file
   holding everything issued so far and nothing after it.  Do not expose the
   segment table, later segment files, the full manuscript, compiled output,
   research records, or earlier reviews.
5. **The supervisor communicates only about process.**  Use the fixed messages
   in `LAUNCHER.md`.  Do not react to the substance, severity, or absence of
   the reader's findings during the relay.
6. **Report delivery is settled before manuscript exposure.** Select
   `reader-persisted` or `supervisor-persisted` delivery as described below.
   The direction and host agent instructions must agree on a permitted method.
   The report must persist between segments in either mode.

Stop the run if the harness cannot create an isolated fresh subagent, retain
it through the relay, or preserve the report by the selected method. Do not
describe the resulting reading as a completed forward-blind review.

This is exposition-review work, not mathematical research. The reader may read
this protocol, the shared exposition standard, and its frozen direction, but
must not load project research state, proof notes, earlier reviews, or drafting
history.

## Roles

**Reader.** A fresh agent, no prior context, follows `DIRECTION.md`. Reads
one segment in order, produces paragraph-anchored editorial annotations,
delivers them by the selected method, stops, and waits. After the final segment
it reviews the complete manuscript against the shared exposition standard and
produces Writing review, Findings, and Verdict without rewriting earlier entries.

**Supervisor.** Prepares the segments, issues them one at a time, persists the
reader's report when that delivery mode is selected, checks process compliance,
and synthesizes at the end.

The supervisor is almost always contaminated — they have read the paper, or
they wrote it.  That is fine, and it is why the checking rules below are
restricted to process.  A supervisor who comments on content is running
their own review through someone else's keyboard.

## What the annotations preserve

The `Reading journal` is a public editorial artifact, not an internal reasoning
transcript. Read in manuscript order and cover every paragraph, but deliver the
annotations at segment boundaries; do not report an exhaustive sequence of
intermediate thoughts, guesses, or calculations. Give assessments and concise
reasons, including mathematical formulas when needed to identify an ambiguity
or missing connection. Natural reviewer language such as "I cannot tell which
object this denotes" is welcome; impersonal prose is not required.

Do not reduce the review to a checklist of demonstrable local errors. Preserve:

- **Purpose and pacing:** a lemma can be perfectly understandable while its
  job remains unexplained for two sections. Record the missing orientation,
  not just undefined terms.
- **Substantive expectations:** an announced pair of comparisons whose second
  member is not identified, or a construction whose relation to the main
  problem is unclear, leaves a real reader question. Anchor such questions
  to the text and audience; do not predict the next paragraph by rote.
- **Cumulative burden:** individually clear symbol choices or local convention
  changes can together make a long argument hard to follow. Cite the earlier
  and current uses rather than requiring one defective sentence.
- **Recoverable but costly exposition:** identify backward searches, ambiguous
  readings, translation into an exact predicate, and missing mathematical
  bridges even when an expert can recover the intended meaning. A concise
  account of the omitted connection is useful; replaying a derivation is not.
- **Harmless postponement and routine compression:** a precise early statement
  can make a proof 1000 lines later harmless. Do not turn every delay, implicit
  step, or reasonable open question into a defect.
- **Effective exposition:** identify examples that make an abstract construction
  concrete, useful convention reminders, and dense proofs made readable by
  explicit reductions and case exhaustion. These passages guide preservation
  and repair; absence of difficulty alone is not a necessity verdict.

Separate the observation from its diagnosis and proposed repair. An uncertain
referent or missing sense of purpose may be recorded before the reader can
settle whether a change is needed. Distinguish routine compression, small
friction, substantive difficulty, and a possible mathematical gap. Not every
annotation is an actionable finding. At a later clarification, link the earlier
entry and assess whether the delay mattered; later understanding does not erase
a first-encounter problem. Append an explicit correction if an earlier review
entry was mistaken, without silently altering its historical text.

## Applying the exposition standard

Record concrete reconstruction burden, not lexical preferences. Use `[idiom]`
when wording requires translation into an exact predicate or uses compressed
inanimate-agency causatives ("Nilpotence writes...", "Linear independence
puts...", "Irreducibility makes...", "kills"), telegraphic imperative chains, or
private shorthand ("projective labels", "Z is intended"), `[meaning]` when it
remains ambiguous, and `[order]` for prose-first violations. At major
boundaries record the preceding and incoming jobs and use `[continuity]` for
missing or delayed handoffs, separately from logical gaps. Do not infer defects
from ordinary stative mathematical subjects ("the functor is exact") or
repeated conventional connectives ("Since", "Then", "Hence").

Apply the shared standard's introduction allowance: harmless background
conventions may wait, but a convention-sensitive assertion or undefined
paper-specific theorem term cannot. Check the separate closing Organization
and Conventions and notation blocks when issued; do not look ahead to excuse
an earlier ambiguity. After the introduction apply ordinary first-use discipline.

## Setup

1. Freeze the manuscript for the duration of the run and create a review
   directory. Follow the host project's policy for temporary and durable
   review artifacts; do not make a temporary review durable without authority.

2. Prepare one ordered reading copy.  For a manuscript built from several
   sources with `\input` or `\include`, flatten them into manuscript order and
   preserve source locators or a small line map, so that findings transfer
   back to the manuscript.

3. Copy both templates into the review directory. Fill all marked fields in
   `DIRECTION.md`, including the paper, audience, and report-delivery fields:

   - **delivery mode and method** — choose one permitted mode below and name
     the writing tool or response/handback channel; do not leave both active.
   - **background** — what the reader is assumed to know.  Pitch this at a
     competent non-specialist in the paper's own area.
   - **withheld** — what the reader must not claim to know.  Start from the
     bibliography: every `\bibitem` key is something the reader has not
     read.  Add any named construction the paper imports.
   - **do-not-read** — the proof thread, any vocabulary or audit report
     beside the paper, compiled output, local copies of the cited sources.
   - **watch-list** — this manuscript's characteristic risks.  Two or three
     lines, prompts for attention, not a checklist.
   - **extra flag categories** — optional.  Add one only when a whole class
     of difficulty would otherwise be invisible in the totals.

4. Confirm the delivery method and isolation permissions before issuing any
   manuscript. Use host permission information or a process-only preflight;
   do not test with manuscript content. If reader file writes are unavailable
   or uncertain, choose a permitted supervisor-persisted response channel.

5. Start the segment table in `LAUNCHER.md` (below), then extract only the
   first segment. Extend the table and cumulative copies as the relay proceeds.

`LAUNCHER.md` must be a separate file, never a section of `DIRECTION.md`
behind a "do not read past this line" marker.  An agent pointed at a file
reads the whole file.

Treat cited sources as unavailable for the run.  The direction must tell the
reader to use only what the manuscript states, so that no gap in the
manuscript is filled from outside it.

## Report delivery

Both modes preserve one report, the same reader, paragraph coverage, and the
append-only history. Delivery does not change the editorial task.

- **`reader-persisted`:** the reader creates and appends the report using the
  permitted tool named in the direction. Its segment reply contains only
  coverage and counts.
- **`supervisor-persisted`:** the reader returns the new report section through
  the response or handback channel named in the direction, followed by coverage
  and counts. The supervisor saves the delivered editorial text without
  substantive alteration before issuing the next segment. Keep process messages
  outside the report. Make the saved report available to that same reader for
  reference. On the first segment include the header; on subsequent segments
  deliver only the new subsection, and at closing only the synthesis sections.

The reader authors the assessments and final synthesis in both modes. The
supervisor checks persistence and preservation of earlier entries; it does not
rewrite, complete, or reconstruct missing reader output. Host-required handback
mechanisms take precedence over assumptions about plain chat replies.

If the selected method fails, stop and record the incomplete run. Do not bypass
execution restrictions through another tool or improvise a demand for an
undelivered journal. Resolve the delivery contract before a fresh run. If a
safety safeguard stops a response, record the failure and do not attempt to
recover or reproduce withheld content. A protocol change is not a guarantee
that any particular model will complete a run.

## Segmenting

A segment is a run of consecutive paragraph blocks.  A block is text between
blank lines; a theorem, definition or proof counts as one block in the usual
way.

Count the blocks in a candidate range:

```bash
awk 'NR>=A && NR<=B && /^[[:space:]]*$/ {c++} END{print c+1 " blocks"}' main.tex
```

Target **6 to 10 blocks per segment**.  Two rules:

- **Only forward.** Never re-cut a range the reader has already read.
- **Never split a proof.** A proof with internal steps is read continuously
  or not at all; cutting it invents a discontinuity the manuscript does not
  have, and "does the proof expose its reductions" is unanswerable from
  half of it.  A long, well-structured proof may exceed 10 blocks.  Let it.

Prefer `\subsection` boundaries.  Include the bibliography in the final
segment — citation apparatus is fair game for a reader who has been
flagging imported results throughout.

Do not fix the whole table before starting.  Size each segment when you
issue it, from the block count of what remains.

## Issuing a segment

Give the reader a **file**, not a line range.  Extract the manuscript from
the beginning through the end of the current segment:

```bash
sed -n "1,${END}p" main.tex > segments/through-<KEY>.tex
```

Cumulative, not per-segment: the direction permits turning back and treats
it as data, so the reader needs everything already read, and nothing after.
Forward-blindness then rests on the filesystem rather than on the reader's
compliance — which matters when the reader is behind a harness you do not
control.

## Running the relay

Create only the first cumulative segment, then spawn one fresh reader and
record its stable identifier.  Send the guide-only initialization message from
`LAUNCHER.md` and nothing else, and wait for the reader to confirm that it has
read the governing guides without opening manuscript text.  Only then send the
first-segment message, again from `LAUNCHER.md` and nothing else.  Any extra
word of guidance is forward information from a contaminated supervisor.

Then loop: receive the segment output, ensure the report is persisted by the
selected method, check process, and issue the next segment with

    Recorded. Next segment: <KEY>, lines <a>--<b>, in <segment file>.

Keep the phrasing **identical every time**.  A terse reply after a clean
segment and a longer one after a weak segment teaches the reader to read
your mood, which is a content channel.

After the last segment, release the synthesis:

    Recorded. The manuscript is finished. Deliver the Writing review,
    Findings, and Verdict sections by the method specified in the direction.

Once a range has been read, never change its boundary or replace the text.  A
review of a modified manuscript is a new run.

## Checking a segment: process only

Check exactly these:

- Did it cover the whole range, block by block?
- Do entries give editorial assessments and concise reasons, rather than
  extended content summaries or internal process transcripts?
- Are passage function, reading assessment, and any substantive outstanding
  question distinguishable? Positive observations and uncertain concerns are
  valid; no difficulty or prediction is required for every paragraph.
- Was the new section saved by the selected method, with earlier entries
  unchanged and any correction or later resolution separately appended?
- Did it use the flag categories, and keep `[continuity]` and `[gap]`
  separate?
- Did it stop at the end of its range?

Verify coverage mechanically rather than by eye.  List the block boundaries
in the range and the reader's entry anchors, and compare:

```bash
awk 'NR>=A && NR<=B && /^[[:space:]]*$/ {printf "%s ", NR}' main.tex; echo
grep -n '^\*\*<KEY>\.' report-*.md
```

Never tell the reader it missed a passage, term or difficulty.  Never
confirm or deny that a flag is correct.  If a process rule was broken, state
the rule and the remedy in one sentence, then issue the next segment in the
fixed form.

## Recompute, never accumulate

Totals — entries, flags, segments — must be recounted from the report file
each time you quote them.  Summing the reader's per-segment reports across a
long relay drifts, and the drift is silent. The following counts historical
journal flags, not unresolved findings: later resolutions and corrections cite
entry IDs without repeating bracketed tags.

```bash
for f in meaning purpose order cite idiom continuity gap; do
  printf "%-8s %s\n" "$f" "$(sed -n '1,/^## Writing review/p' report-*.md | grep -o "\[$f\]" | wc -l)"
done
```

## Process cautions

Keep launcher state out of reader files and supervisor replies process-only.
Reader replies carry annotations only in supervisor-persisted mode. Entry
counts reflect paragraph structure, not diligence; few flags or a quick segment
do not establish fatigue. Check coverage against blocks. Never demand more
criticism or more detailed thought processes to demonstrate effort. A direction
cannot override higher-priority execution restrictions.

## The deliverable

The report has four parts.  The journal is the evidence base.  Writing review
applies the shared exposition standard to the manuscript's first-encounter
evidence; it is not a second-pass necessity or referential-precision audit.
Findings and Verdict are what you revise from: Findings should be ranked and
anchored, and the Verdict should say where first-reading rhythm broke or flowed
and what reconstruction burden remained. Include a compact continuity map of
the major boundaries, distinguishing seamless or compressed-but-natural
handoffs from abrupt, interruptive, delayed, or displaced ones. Do not treat
absence of friction as evidence that every passage earns its space or uses the
most precise mathematical interface; that is the separate skeptical-editor
test.

Give the distilled findings stable identifiers `FR-1`, `FR-2`, and so on, and
list their supporting journal entry identifiers. Group repeated instances by
cause, but represent every distinct objective burden recorded in the journal
or Writing review by one finding. Preserve useful positive observations and
unresolved questions in the Writing review without automatically turning them
into repair demands. A corrected reviewer mistake is not an outstanding defect;
retain the original entry and its correction link. Begin the Verdict with the
literal line
`Continuous-reader verdict: PASS` or
`Continuous-reader verdict: FAIL`; use `FAIL` when an objective finding
requires manuscript change for the stated audience to follow the paper on
first encounter. The writer may disagree later, but must preserve this literal
verdict and adjudicate every finding.

Read the whole report before acting.  Then look for *causes* rather than
working the list: thirty findings usually have three or four sources, and
repairing the sources converts most of the list into non-issues.  A list of
defects is not a revision plan.

The supervisor may disagree with the reader's diagnosis or proposed repair,
and should say so explicitly when synthesizing. It must not erase a recorded
reading difficulty, backward search, translation burden, or cumulative loss of
orientation merely because an expert can recover the intended meaning. Preserve
the reported observation separately from the diagnosis and repair; neither the
reader's proposed repair nor every uncertain concern is automatically binding.
