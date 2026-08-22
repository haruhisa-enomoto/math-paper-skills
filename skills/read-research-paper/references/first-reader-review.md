# Continuous first-reader review

Read this guide before running or supervising a first-reader review of a
manuscript.  It describes a relay protocol in which one reader reads a paper
in order, without ever seeing what comes later, and a supervisor issues the
paper to it one segment at a time.

This is a test of exposition, not of truth.  It answers: can a competent
reader who does not know the cited sources follow this paper on a first
pass?  It does not answer whether the mathematics is correct.  A proof audit
is a different task with a different protocol; do not merge them.  It also
does not decide whether every understandable passage earns its space.  Use
[skeptical-editor protocol](skeptical-editor-review.md) for that independent
whole-manuscript test.

Reusable direction and launcher templates ship with the writer skill as
[first-reader direction](../../write-research-paper/assets/first-reader-direction.md)
and [first-reader launcher](../../write-research-paper/assets/first-reader-launcher.md).
The writing standards the review applies are in the
[mathematical paper-writing guide](../../write-research-paper/references/paper-writing.md);
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
   In the Codex collaboration tool, use `fork_turns: "none"`.
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

Stop the run if the harness cannot create an isolated fresh subagent, retain
it through the relay, or let it write the persistent report.  Do not describe
the resulting reading as forward-blind.

This is exposition-review work, not mathematical research. The reader may read
this protocol, the portable paper-writing guide, and its frozen direction, but
must not load project research state, proof notes, earlier reviews, or drafting
history.

## Roles

**Reader.** A fresh agent, no prior context, follows `DIRECTION.md`.  Reads
one segment, appends a journal, stops, waits.  After the final segment it
reviews the complete manuscript against the portable paper-writing guide and appends Writing
review, Findings, and Verdict without changing the journal.

**Supervisor.** Prepares the segments, issues them one at a time, checks
each report for process compliance, and synthesizes at the end.

The supervisor is almost always contaminated — they have read the paper, or
they wrote it.  That is fine, and it is why the checking rules below are
restricted to process.  A supervisor who comments on content is running
their own review through someone else's keyboard.

## Setup

1. Freeze the manuscript for the duration of the run and create a review
   directory. Follow the host project's policy for temporary and durable
   review artifacts; do not make a temporary review durable without authority.

2. Prepare one ordered reading copy.  For a manuscript built from several
   sources with `\input` or `\include`, flatten them into manuscript order and
   preserve source locators or a small line map, so that findings transfer
   back to the manuscript.

3. Copy both templates into the review directory.  Fill the five slots in
   `DIRECTION.md`:

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

4. Build the segment table in `LAUNCHER.md` (below), then extract the
   segment files.

`LAUNCHER.md` must be a separate file, never a section of `DIRECTION.md`
behind a "do not read past this line" marker.  An agent pointed at a file
reads the whole file.

Treat cited sources as unavailable for the run.  A fresh subagent may still
carry general or source-specific knowledge from training; the direction must
forbid using recalled source content to fill a gap in the manuscript.

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

Then loop: receive the report, check process, issue the next segment with

    Recorded. Next segment: <KEY>, lines <a>--<b>, in <segment file>.

Keep the phrasing **identical every time**.  A terse reply after a clean
segment and a longer one after a weak segment teaches the reader to read
your mood, which is a content channel.

After the last segment, release the synthesis:

    Recorded. The manuscript is finished. Append the Writing review,
    Findings, and Verdict sections as specified in the direction.

Once a range has been read, never change its boundary or replace the text.  A
review of a modified manuscript is a new run.

## Checking a segment: process only

Check exactly these:

- Did it cover the whole range, block by block?
- Are entries reading experience, or have they drifted into content summary?
- Do they distinguish what the manuscript communicated from what the reader
  had to infer, reconstruct, or recover by rereading?
- Did it append, rather than rewrite the file?
- Did it use the flag categories, and keep `[gap]` separate?
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
long relay drifts, and the drift is silent.

```bash
for f in meaning purpose order cite idiom gap; do
  printf "%-8s %s\n" "$f" "$(sed -n '1,/^## Writing review/p' report-*.md | grep -o "\[$f\]" | wc -l)"
done
```

## Known failure modes

Each of these cost a real run or a wrong call.

1. **Launcher content in the reader's file.** A segment table below a "for
   the launcher only" divider inside `DIRECTION.md` was read in one pass,
   compromising every "what do I expect next" entry.  Separate files.
2. **Initialization and the first segment sent together.** A reader told to
   read the guides and open segment 1 in one message reads them in whatever
   order it likes, and often opens the manuscript first.  Initialize, wait for
   the readiness reply, then issue the segment.
3. **The reader's harness refuses to write a report file.** Some agent
   system prompts forbid creating report or documentation files.  The
   direction must override this explicitly and offer a shell-append
   fallback.
4. **A reply carrying findings.** If the reader summarizes its findings back
   to you, you will be tempted to react, and your reaction leaks.  Restrict
   replies to range, entry count, and flag counts.
5. **Entry count read as effort.** Entry count tracks the manuscript's
   paragraph structure, not the reader's diligence.  A segment with five
   entries may be five blocks long.  Verify against blocks before
   concluding anything.
6. **Fast, low-flag segment read as fatigue.** A well-structured proof
   generates few flags and few turn-backs, and finishes quickly.  Read an
   entry before deciding the reader faded.

## The deliverable

The report has four parts.  The journal is the evidence base.  Writing review
applies the portable paper-writing guide to the manuscript's first-encounter evidence; it is
not a second-pass deletion audit.  Findings and Verdict are what you revise
from: Findings should be ranked and anchored, and the Verdict should say where
first-reading rhythm broke or flowed and what reconstruction burden remained.
Do not treat absence of friction as evidence that every passage earns its
space; that is the separate skeptical-editor test.

Read the whole report before acting.  Then look for *causes* rather than
working the list: thirty findings usually have three or four sources, and
repairing the sources converts most of the list into non-issues.  A list of
defects is not a revision plan.

The supervisor may disagree with the reader, and should say so explicitly
when synthesizing.  A first reader's judgement about what a paper needs is
weaker than its report of where it stumbled; the stumble is data, the
prescription is opinion.
