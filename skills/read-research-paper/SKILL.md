---
name: read-research-paper
description: Run an independent exposition review of a frozen mathematics manuscript as a forward-blind continuous first reader, a whole-paper skeptical editor, or a bounded delta-regression reader. Use to collect first-pass readability, whole-paper necessity and referential-precision, or repair-regression evidence without editing; do not use to summarize a paper, verify proofs, assess novelty, adjudicate repairs, or review an unstable draft.
---

# Read a research paper

Act only as an independent exposition reviewer in the assigned mode. Report
first-encounter reading evidence, whole-paper editorial necessity and
referential precision, or bounded regression evidence as appropriate. Never
edit or adjudicate the manuscript.

## Validate the run before reading

Require an explicit mode: `continuous`, `editorial`, or `delta`.

Confirm all of the following:

- this is a fresh context without the writer's conversation or diagnoses;
- the manuscript packet is frozen and identifies its revision; editorial mode
  also identifies a reading-copy content hash;
- the allowed text, assumed background, report destination, and withheld
  material are explicit; and
- the execution surface cannot modify the manuscript.

Read the paired writer skill's
[mathematical paper-writing guide](../write-research-paper/references/paper-writing.md)
in full, then the mode-specific reference named below. Resolve these links
relative to this skill directory. Do **not** read the writer workflow, owner
decision state, research ledgers or notes, earlier reviews, drafting history,
version-control history, evaluation fixtures, or any host-project paper-writing
overlay that contains writer-only state. If this context has already seen
those materials, stop and ask the supervisor for a fresh isolated reader. Do
not simulate freshness.

## Continuous mode

Follow the [continuous first-reader protocol](references/first-reader-review.md)
and the supervisor's frozen direction.

Complete the governing guides and task direction before receiving any
manuscript segment. Confirm readiness to the supervisor, then accept the first
cumulative segment. If the initialization message exposes a segment path or
manuscript text, stop and mark the run invalid rather than trying to serialize
the two tasks yourself.

- Keep one reader identity for the whole manuscript.
- Receive only cumulative segments in document order. Journal the newly issued
  range while retaining earlier text for continuity.
- Never inspect later text, the complete source, compiled output, literature,
  launcher state, expected findings, or prior reports.
- Record each stumble where it occurs, including the inference or rereading
  required. Preserve earlier entries when later text resolves them.
- Report concrete first-encounter reconstruction burden, evidence-status
  confusion, or purpose, placement, and order friction. Test each sentence in
  its paragraph and each paragraph in the document path. Do not manufacture a
  defect from a lexical or content category alone; explain what the intended
  reader cannot recover and why it matters at that point.
- Do not convert absence of a stumble into a keep/delete judgment. A clear
  passage may still fail the separate whole-paper necessity or
  referential-precision audit.
- Stop at the issued boundary and wait for the same process-only supervisor.

If the host cannot resume the same isolated reader across segments, mark the
run invalid; fresh section readers are not a continuous forward-blind review.
After the final segment, synthesize the immutable journal using the continuous
protocol. Keep observed reading evidence separate from repair suggestions.

## Editorial mode

Use editorial mode only on a nearly final complete manuscript. Follow the
[skeptical-editor protocol](references/skeptical-editor-review.md) and the
supervisor's frozen direction.

Complete the governing guides and task direction before receiving manuscript
text. Confirm readiness, then accept the complete frozen reading-order
manuscript in a second message. If initialization exposes the manuscript path
or text, stop and mark the run invalid.

Before reading, recompute the supplied file's content hash by the method named
in the direction and compare it with the recorded reading-copy identity. Do not
substitute a statement that the packet appears consistent. A mismatch makes
the run invalid.

- Read the complete paper once to recover its promise, result hierarchy,
  section jobs, intended audience, and detail budget.
- Read it again under two coupled audits: identify the exact reader-visible
  loss, if any, caused by deleting a passage, and test whether every retained
  substantive statement or result pointer gives an exact subject, predicate,
  status, and referent without requiring guesswork.
- Audit every explicit remark, negative or defensive scope qualification,
  recurring informal alias, phrase presented as a named theorem, criterion,
  principle, method, or argument, and wording that hides an exact mathematical
  predicate or result behind a descriptive phrase, citation, or loose pointer.
- Distinguish `clear` from `worth retaining`. Truth, relevance, and a
  reconstructible purpose do not by themselves establish reader benefit.
- Distinguish `understandable` from `referentially precise`. A reader's ability
  to guess the intended theorem or predicate does not validate the wording; a
  necessary passage may merit `rename` or `replace` rather than compression or
  deletion.
- Do not optimize raw word count, rewrite passages, or remove necessary
  mathematical context. Explain the marginal reader value before assigning an
  editorial category, and explain the exact ambiguity or reconstruction burden
  before assigning a precision category.

Report the recovered contract, section audit, mandatory necessity and
referential-precision inventories, ranked findings, and overall verdict
required by the protocol. Keep objective exposition defects separate from
owner-judgment questions.

## Delta mode

Use delta mode only after a bounded accepted repair. Receive, in document
order:

- base and changed revision identifiers;
- each changed region with enough preceding and following context;
- the cold-reader success criterion for each repair cluster; and
- explicit non-scope, without the diagnosis, preferred wording, or gold answer.

For each cluster report what the passage now communicates; whether the
criterion passes, fails, or is untestable; what reconstruction remains; and
whether the edit introduced ambiguity, process leakage, over-definition,
displaced motivation, boilerplate, conflict, or out-of-scope change. Do not
rewrite the passage. A brief repair direction is allowed only to explain a
failure and must remain separate from the evidence.

If the packet changes the paper promise, structural front matter, section
order, or reading path, report that delta mode is insufficient and a new
continuous read is required.

## Report scope

Record mode, exact revision, material actually read, isolation conditions, and
completion state. Silence is not endorsement; flag counts are not a quality
score; a possible gap is not a mathematical verdict; and a passed delta does
not certify unchanged text. A passed editorial review does not certify
first-encounter readability. State the concrete reader burden or marginal
reader value before assigning a category or suggesting a repair.
