# First-reader review: direction

<!--
TEMPLATE. Fill all fields marked {{ }} and delete these comments.
Select one report-delivery mode and its permitted tool or response channel
before launch; remove the unselected mode's instructions from the filled copy.
Use with the `read-research-paper` skill in `continuous` mode. Keep
LAUNCHER.md as a SEPARATE file:
never put the segment table in this one, not even behind a divider.
-->

This document is the complete review-specific direction for a first-reader
review of {{PAPER}}, subject to the governing harness, safety, and host-project
rules. If those rules prevent isolation or the report-delivery method selected
below, tell the supervisor and stop the run. Do not work around execution
restrictions or substitute another delivery method mid-run.

This is exposition-review work, not mathematical research. Do not load the
project's research state, proof notes, drafting history, earlier reviews, or
evaluation fixtures.

Before you receive any manuscript text, activate `read-research-paper` in
`continuous` mode and read its `SKILL.md`, the shared exposition standard,
and the continuous first-reader protocol completely. They contain no
manuscript content. Validate isolation and the selected delivery contract, then
confirm readiness to the supervisor and wait; do not open a segment before that
exchange.

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
learn what the source says.  Use only what the manuscript states: do not
supply a definition, hypothesis, or argument that it has not yet given.

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
- Do not silently repair prose. Report avoidable rereading or a missing
  connection instead of fixing the text. Distinguish this burden from routine
  implicit steps appropriate to the stated audience.

If you open `LAUNCHER.md` or any later text, tell the supervisor immediately
and stop.  The run is invalid and cannot be repaired by continuing.

## Your assigned segment (hard rule)

Each supervisor message names a segment key and a line range, and points you
at a file containing the manuscript from the beginning through the end of
that segment, and nothing after it.

- Annotate only the new range. You may re-read anything earlier in the file.
- Do not guess what comes after your segment. Record substantive questions
  raised by the text under item (c), without inventing a prediction for every
  paragraph.
- When you have reported, stop and wait.  Do not begin the next segment on
  your own initiative.

The macro preamble is an exception: it is a lookup table, not reading
material.  Consult it whenever a macro is unclear, at any time.

## Forward-blindness (the point of this review)

Never use information from later in the paper to excuse an earlier sentence.
Two rules are yours to keep:

1. **Preserve earlier assessments.** Do not edit or soften an earlier entry
   after later text explains the difficulty. Append a resolution note where
   the explanation occurs, linking both passages. Assess whether the delay
   imposed a burden: a precise early statement can make a much later proof
   harmless. If an earlier review entry was mistaken, append an explicit
   correction and its reason rather than silently rewriting it.
2. **Turning back is allowed.** When a passage requires a backward search,
   identify the current passage and the earlier definition or result needed.
   Distinguish a useful, adequately referenced recall from an avoidable search.

## Reading protocol

Read your segment paragraph by paragraph, in order, assessing each passage
using only the audience background and text available up to that point. A
paragraph is a block of text separated by blank lines; displayed formulas
belong to the paragraph around them; a theorem, lemma, definition, remark, or
proof counts as one or more paragraphs in the usual way.

Produce paragraph-anchored first-pass editorial annotations and deliver them
at the segment boundary. The report's `Reading journal` is an editorial
artifact, not an internal reasoning transcript. Do not provide an exhaustive
sequence of intermediate thoughts, guesses, or calculations. Give assessments
and concise reasons; formulas may identify a missing connection or ambiguity.
Natural reviewer language such as "I cannot tell which object this denotes"
is welcome. Follow the protocol's "What the annotations preserve" guidance.

Cover every paragraph with an entry whose components are:

  (a) Passage function: briefly identify what the paragraph states or does.
  (b) Reading assessment: difficulties or particularly effective exposition,
      with concise reasons. Distinguish routine compression, small friction,
      substantive difficulty, and a possible mathematical gap. Identify the
      missing referent, connection, convention, or purpose where possible.
  (c) Outstanding question or promised follow-up, only when substantive:
      record what the text leaves unresolved for the stated audience. This
      need not be an explicit promise or already-established defect. Link a
      later clarification to this entry; do not predict the next paragraph
      by rote.

Do not reduce (b) to a local-error checklist. Preserve purpose and pacing,
substantive expectation mismatches, cumulative notation and convention load,
recoverable but costly exposition, harmless postponement, and examples or
proof organization that make difficult material clear. A passage can be
locally understandable yet leave its role unclear. Several locally clear
choices can impose a cumulative burden; anchor that observation to multiple
passages. Separate the observation from its diagnosis and any proposed repair.

At every major section or subsection boundary, first check that the new
section begins with ordinary prose before any formal environment, display,
list, or nested heading; record a violation as `[order]`. Also keep the
preceding passage's job active and assess the heading together with the opening
prose and first formal statement. Say whether the handoff is seamless,
compressed but natural, abrupt, interruptive, delayed, or displaced, and
identify the connection the manuscript supplied or left to you. A generic
roadmap sentence can pass the structural check while failing this continuity
test, so do not reward boilerplate.

Length rule: use one line for a passage with no substantive observation.
Expand only for a useful difficulty, outstanding question, resolution, or
specific positive observation—not an extended mathematical summary. Do not
require a flag or an item (c) for every paragraph, and omit empty field labels.

If the text fails to deliver an announced follow-up, or leaves a reasonable
reader question unresolved, assess the resulting burden. A change of route
may be well signposted, and postponement may be harmless. Record uncertain
concerns without converting every observation into a mandatory repair.

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

Report a difficulty even when none of these tags fits. In the journal, use
bracketed tags only for newly reported difficulties; resolution and correction
notes cite earlier entry IDs without repeating their tags. Historical flag
counts are not counts of unresolved findings.

## Report

- Delivery mode: {{DELIVERY_MODE — reader-persisted OR supervisor-persisted}}
- Permitted delivery method: {{DELIVERY_METHOD — writing tool OR response/handback channel}}

There is ONE markdown report in this directory, named

    report-<agent-label>-<YYYY-MM-DD>.md

where `<agent-label>` is given in your initialization message. Take the date
from the operating system. You author the report in either mode:

- **`reader-persisted`:** create and append the report using the named permitted
  tool. Reply only with the short coverage summary specified below.
- **`supervisor-persisted`:** do not write the file. Deliver the new editorial
  report section through the named response or handback channel, then the short
  coverage summary. The supervisor saves the report section without substantive
  alteration before issuing the next segment. You may read the saved report.
  Host-required handback mechanisms apply even when plain replies are not
  delivered to the supervisor.

On the first segment supply the header below plus that segment's annotations.
On every later segment supply only the new subsection. Preserve earlier text;
append any resolution or correction separately. The delivery mode changes who
persists the report, not its content or your isolation obligations. If the
selected method fails, report the process failure and stop. Do not improvise a
new channel or attempt to recover or reproduce content withheld by a safeguard.

    # First reader report: <paper>
    Date: <OS timestamp>
    Agent: <agent-label>
    Scope: <reading-copy path>
    Delivery: <selected mode and method>

    ## Reading journal

    ### <KEY> (lines <a>--<b>)
    (entries anchored by opening phrase and lines, starting **<KEY>.1**, **<KEY>.2**, ...)

After each segment include a short coverage summary: the range covered, the
number of entries, and the count of each new flag raised. In reader-persisted
mode this is the entire reply; in supervisor-persisted mode it follows the new
report section and stays outside the saved report. Do not add a separate
findings recap or repeat earlier sections.

When the supervisor says the manuscript is finished, deliver these sections
by the selected method (append directly or return for the supervisor to append):

    ## Writing review
    (the complete manuscript against the sections of the shared
    exposition standard, restricted to first-encounter evidence, with
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

Writing review, Findings, and Verdict may draw on the whole journal—that
is synthesis, not a forward-blindness violation. The earlier entries stay as
written. Preserve useful positive observations and unresolved questions in the
Writing review without making them automatic repair demands. Distinguish a
later resolution from a correction of a reviewer mistake; a corrected mistake
is not an outstanding defect.

Quote opening phrases rather than relying on line numbers alone; line
numbers drift.

Report small local friction too.  A recurring small defect is evidence that
the exposition needs a broader repair, and the supervisor decides that.
