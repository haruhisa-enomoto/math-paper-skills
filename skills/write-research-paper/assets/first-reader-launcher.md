# Launcher notes: first-reader review

<!--
TEMPLATE. Use with the `write-research-paper` and `read-research-paper` skills.
This file is for the supervisor.  Readers are forbidden to open it by
DIRECTION.md.  Never merge it into DIRECTION.md: an agent pointed at a file
reads the whole file, so a "do not read past this line" marker is not a
boundary.
-->

**Readers must not open this file.**  It holds the segment table, which
tells you the shape of the rest of the paper.

## Setup

- [ ] The manuscript is frozen for this run.
- [ ] The reading copy contains the manuscript in reading order.  `\input`
      and `\include` files have been flattened, and source locators or a line
      map have been preserved.
- [ ] `DIRECTION.md` is filled and contains no suspected defects, desired
      conclusions, later outline, or segment information.
- [ ] `DIRECTION.md` tells the reader to load `read-research-paper` in
      `continuous` mode and read its portable guides before the manuscript.
- [ ] Later cumulative segment files have not been created.
- [ ] You can spawn one subagent with no inherited conversation and can
      reactivate that same subagent for the whole relay.

If any item fails, fix the setup before launching.  Record an aborted run and
its cause in the run log.

## Reader identity

Spawn exactly one new subagent.  Explicitly select no inherited conversation
turns or research context; do not rely on a harness default that forks the
supervisor's context.  In Codex, set `fork_turns: "none"`.  In Claude Code,
use a fresh agent or session rather than a fork agent.  On another harness,
use its equivalent no-inherited-context option.  Record the stable identity
the harness returns:

    Reader label:
    Subagent identity:
    Launch time:

Use this same subagent for every continuation and for the final synthesis.  Do
not replace it between segments.  A second opinion is a separate complete run
by another fresh reader, never a division of one run among several.

## Segment table

Size each segment when you issue it, from the block count of what remains —
do not fix the whole table in advance.  Target 6 to 10 blocks; only forward;
never split a proof.  Record what you issued:

| Key | Scope | Lines | Blocks | Segment file |
|-----|-------|-------|--------|--------------|
|     |       |       |        |              |

Block count for a candidate range:

```bash
awk 'NR>=A && NR<=B && /^[[:space:]]*$/ {c++} END{print c+1 " blocks"}' <paper>
```

Segment file to hand over (cumulative — everything read so far, nothing
after):

```bash
sed -n "1,${END}p" <paper> > segments/through-<KEY>.tex
```

Check that the file ends at the recorded boundary and holds no later text
before giving it to the reader.

## Initialize the reader

Send this message, and nothing else, to the fresh subagent:

    You are the reader in a forward-blind first-reader review.  This is
    exposition-review work, not mathematical research: do not load the
    project's mathematical boot state.  Your agent label: <LABEL>.
    Load the read-research-paper skill in continuous mode. Read
    <path>/DIRECTION.md and
    every guide the skill and direction require, completely. Do not open or
    receive any manuscript segment yet. Validate the isolation conditions,
    then reply only: Ready for the first segment.

Do not include a segment key, range, path, or manuscript text here.  Any
added explanation is forward information from a contaminated supervisor.

## Launch the first segment

After the same reader replies `Ready for the first segment`, send exactly:

    First segment: <KEY>, lines <a>--<b>, in <segment file>.

If the reader opens manuscript text before confirming readiness, mark the run
invalid and start a new run with a new reader.  Do not try to serialize the
two steps by combining them into one message.

## Checking a segment: process only

The launcher has usually read the manuscript, or wrote it.  Both are
contaminated.  The check is therefore restricted to process.

- Did the reader cover the whole range, block by block?
- Are entries reading experience, or content summary?
- Did it distinguish what the manuscript communicated from what it had to
  infer, reconstruct, or recover by rereading?
- Did it append rather than rewrite?
- Did it use the flag categories, and keep `[gap]` separate?
- Did it stop at the end of its range?

Verify coverage mechanically:

```bash
awk 'NR>=A && NR<=B && /^[[:space:]]*$/ {printf "%s ", NR}' <paper>; echo
grep -n '^\*\*<KEY>\.' report-*.md
```

Never say or hint that the reader missed a passage, term, or difficulty.
Never confirm or deny that a flag is correct.

Approvals must be uniform in tone and length, so the reader cannot infer
approval or disappointment from how the next message reads:

    Recorded. Next segment: <KEY>, lines <a>--<b>, in <segment file>.

If a process rule was broken, state the rule and the remedy in one sentence,
then give the same fixed form.

If the reader opens withheld material, cannot append the report, or loses its
identity or context between segments, stop and mark the run invalid.  Do not
continue it under a replacement reader.

## Closing

    Recorded. The manuscript is finished. Append the Writing review,
    Findings, and Verdict sections as specified in the direction.

The reader, not the supervisor, synthesizes its journal.  Interpret the report
and decide the revisions after it finishes.

## Totals

Recompute from the report file; never accumulate across turns.

```bash
for f in meaning purpose order cite idiom continuity gap; do
  printf "%-8s %s\n" "$f" "$(sed -n '1,/^## Writing review/p' report-*.md | grep -o "\[$f\]" | wc -l)"
done
```

## Run log

Record aborted runs and the setup defect that caused them.  These are the
part of the protocol that cannot be reconstructed from first principles.

    Status: complete | invalid | aborted
    Reader identity:
    Reading-copy identity:
    Issued segments:
    Failure and point of discovery, if any:
