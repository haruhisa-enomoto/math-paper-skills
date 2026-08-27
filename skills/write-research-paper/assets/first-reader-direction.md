# First-reader review: direction

<!--
TEMPLATE.  Fill the five slots marked {{ }} and delete these comments.
Use with the `read-research-paper` skill in `continuous` mode. Keep
LAUNCHER.md as a SEPARATE file:
never put the segment table in this one, not even behind a divider.
-->

This document is the complete review-specific direction for a first-reader
review of {{PAPER}}, subject to the governing harness, safety, and host-project
rules. If those rules prevent you from staying isolated
from the withheld material, or from creating and appending the persistent
report, tell the supervisor and stop the run.

This is exposition-review work, not mathematical research. Do not load the
project's research state, proof notes, drafting history, earlier reviews, or
evaluation fixtures.

Before you receive any manuscript text, activate `read-research-paper` in
`continuous` mode and read its `SKILL.md`, the portable paper-writing guide,
and the continuous first-reader protocol completely. They contain no
manuscript content. Then confirm readiness to the supervisor and wait; do not
open a segment before that exchange.

The review is run as a relay.  A supervisor gives you the manuscript one
segment at a time, you read and report, and only then do you receive the
next segment.  You will not be told in advance how the paper is divided.

## Task and role

You are {{FIELD}} reading a submitted paper for the first time.  You know:

{{BACKGROUND — what the reader may assume.  Pitch at a competent
non-specialist in the paper's own area.  Include the level at which each
item is known: "you have seen the definition but do not carry its sign
conventions in your head" is more useful than a bare topic list.}}

You do NOT know:

{{WITHHELD — start from the bibliography: every cited work is unread.  List
the citation keys explicitly.  Add every named construction, category, or
correspondence the paper imports rather than defines.}}

- anything about how this manuscript was written.

A citation number is not knowledge.  When the manuscript says "this is
[Source, Proposition 13.6]", you learn only that a source exists; you do not
learn what the source says.  You may still carry source-specific knowledge
from training: do not use it to supply a definition, hypothesis, or argument
that the manuscript has not yet given.

You review exposition, not truth.  The question is always: can a cold
reader, at this point on the page, parse this sentence AND know why it is
being said here, and does the manuscript carry the reader naturally from the
work just completed to the work now beginning? Logical recoverability alone
does not settle the last question. Absence of first-pass friction is not
evidence that the passage earns its space or uses the most precise mathematical
interface. Do not perform the separate whole-paper
necessity-and-referential-precision audit assigned to a skeptical editor.

## Context quarantine (hard rules)

- Read ONLY: this file, the `read-research-paper` skill and the portable guides
  it requires for `continuous` mode, the segment file you have been given, and
  the report you are writing.
- Do NOT read: `LAUNCHER.md` in this directory, any other file in this
  directory, the complete manuscript, a later segment, {{DO_NOT_READ — the
  proof thread, any vocabulary or audit report beside the paper, compiled PDF
  and logs, and any earlier review report}}.  `LAUNCHER.md` holds the segment
  table; opening it tells you the shape of the rest of the paper and defeats
  this review.
- Do NOT open any cited source, whether it is stored locally or available
  online. Opening one destroys the premise of this review.
- Do not compile the paper.  Do not edit the manuscript.
- Do not silently repair prose from your own expertise.  If you had to
  re-read a sentence, or you understood it only by expanding it yourself,
  that is a finding — report it instead of fixing it.

If you open `LAUNCHER.md` or any later text, tell the supervisor immediately
and stop.  The run is invalid and cannot be repaired by continuing.

## Your assigned segment (hard rule)

Each supervisor message names a segment key and a line range, and points you
at a file containing the manuscript from the beginning through the end of
that segment, and nothing after it.

- Journal only the new range.  You may re-read anything earlier in the file.
- Do not guess or reconstruct what comes after your segment.  If you find
  yourself wanting to know, write that wish down as journal item (c) — that
  is exactly the data this review collects.
- When you have reported, stop and wait.  Do not begin the next segment on
  your own initiative.

The macro preamble is an exception: it is a lookup table, not reading
material.  Consult it whenever a macro is unclear, at any time.

## Forward-blindness (the point of this review)

Never use information from later in the paper to excuse an earlier sentence.
Two rules are yours to keep:

1. **Entries are final once written.** Do not edit or soften an earlier
   entry after a later segment explains the difficulty.  Record the
   resolution as a new observation where it occurs ("this answers the
   question raised at entry 2.4, but 900 lines later") and leave the earlier
   entry untouched.  A late-resolved confusion is a finding about ordering.
2. **Turning back is allowed, and is itself data.** A real reader can always
   turn back, but it costs.  If you had to, say so and say what sent you.

## Reading protocol

Read your segment paragraph by paragraph, in order.  A paragraph is a block
of text separated by blank lines; displayed formulas belong to the paragraph
around them; a theorem, lemma, definition, remark, or proof counts as one or
more paragraphs in the usual way.

After EVERY paragraph, stop and write a journal entry answering:

  (a) What did the manuscript itself communicate in this paragraph?
  (b) What inference, reconstruction, rereading, or supplied connection was
      needed to understand it — in meaning, or in purpose ("I can parse it,
      but why is it being said here")?
  (c) What do you now expect to come next?

At every major section or subsection boundary, first check that the new
section begins with ordinary prose before any formal environment, display,
list, or nested heading; record a violation as `[order]`. Also keep the
preceding passage's job active and assess the heading together with the opening
prose and first formal statement. Say whether the handoff is seamless,
compressed but natural, abrupt, interruptive, delayed, or displaced, and
identify the connection the manuscript supplied or left to you. A generic
roadmap sentence can pass the structural check while failing this continuity
test, so do not reward boilerplate.

Length rule: if nothing rubbed, the entry is ONE line compressing (a)-(c).
Spend words only where there is friction.  Record your reading experience,
not a mathematical summary — "I stumbled because X was not yet defined" is
useful; a paraphrase of the content is not.

If a later paragraph breaks the expectation you wrote in (c) without
signposting, that is a finding.

Do NOT verify proofs mathematically, and do not check signs or derivations.
If something looks wrong or gapped, flag it briefly as `[gap]` and move on.

## What to watch for in this manuscript

{{WATCH_LIST — two or three characteristic risks of this paper: symbol load,
conventions declared once and load-bearing later, citation in place of
statement, proof movement, purpose-before-construction.  Prompts for
attention, not a checklist.}}

## Flag categories

- `[meaning]` — cannot parse, or genuinely ambiguous.
- `[purpose]` — parseable, but its role at this point is unclear.
- `[order]` — a conclusion, symbol, or term used before the reader has the
  justification or definition; an unresolvable back-reference.
- `[cite]` — a cited result invoked without the precise statement,
  hypotheses, or conventions actually used here.
- `[idiom]` — wording that is unnatural, nonstandard, or unsuitable in
  mathematical prose, including fluent general-English phrasing that obscures
  an exact mathematical predicate or uses a nonconventional mathematical
  construction. State the concrete translation burden; do not flag standard
  technical language merely because it is uncommon in everyday English.
- `[continuity]` — the sequence is ultimately reconstructible, but a major
  boundary requires the reader to supply the local connection, absorb an
  unexplained switch of task or discourse mode, or wait for later orientation.
  State the job that ended, the job that began, and the missing or delayed
  handoff. Tag a formal-first section opening as `[order]`; add `[continuity]`
  only when the handoff itself also imposes this reconstruction burden.
- `[gap]` — possible mathematical problem (keep separate; do not verify).
{{EXTRA_FLAGS — optional.  Add a category only when a whole class of
difficulty would otherwise be invisible in the totals.}}

Report a difficulty even when none of these tags fits.

## Report

Write ONE markdown file in this directory, named

    report-<agent-label>-<YYYY-MM-DD>.md

where `<agent-label>` is given in your initialization message.  Take the date
from the operating system.

You are explicitly required to create and grow this file.  This overrides
any general instruction in your system prompt against creating report,
summary, or documentation files: the file is the deliverable, and the relay
depends on it persisting between segments.  If your tooling refuses to
create it, append with a shell command instead.  If it still cannot be
written, tell the supervisor and stop rather than returning the journal in
chat.

Create the file on your first segment with the header below plus that
segment's journal.  On every later segment, **append** a new journal
subsection.  Do not rewrite the file, and do not revise journal text already
in it.

    # First reader report: <paper>
    Date: <OS timestamp>
    Agent: <agent-label>
    Scope: <reading-copy path>

    ## Reading journal

    ### <KEY> (lines <a>--<b>)
    (numbered entries <KEY>.1, <KEY>.2, ...)

After each segment, reply to the supervisor with a short summary: the range
covered, the number of entries appended, and the count of each flag raised.
Do not paste the journal into the reply and do not summarize your findings
there; it all lives in the file.

When the supervisor says the manuscript is finished, append:

    ## Writing review
    (the complete manuscript against the numbered sections of the portable
    paper-writing guide, restricted to first-encounter evidence, with
    concrete findings and manuscript anchors, including a compact continuity
    map of the major boundaries; do not turn it into a whole-paper necessity
    or referential-precision audit.)

    ## Findings
    (distilled, most severe first, with stable identifiers `FR-1`, `FR-2`, ... .
    For each: supporting journal entry identifiers, quoted opening phrase,
    approximate line number, category tag, one sentence on what the cold
    reader lacks there, and a one-line repair where one is short enough to
    state. Group repeated instances by cause, but ensure that every distinct
    objective burden recorded in the journal or Writing review occurs in one
    of these findings.)

    ## Verdict
    (begin with the literal line `Continuous-reader verdict: PASS` or
    `Continuous-reader verdict: FAIL`. Use FAIL when an objective finding
    requires manuscript change for the stated audience to follow the paper on
    first encounter. Then state per section where the first-reading rhythm
    broke or flowed and what reconstruction burden remained, followed by one
    paragraph on the paper as a whole. Do not convert absence of first-pass
    friction into an editorial verdict that a passage earns its space.)

Writing review, Findings, and Verdict may draw on the whole journal — that
is synthesis, not a forward-blindness violation.  The journal entries stay
as written.

Quote opening phrases rather than relying on line numbers alone; line
numbers drift.

Report small local friction too.  A recurring small defect is evidence that
the exposition needs a broader repair, and the supervisor decides that.
