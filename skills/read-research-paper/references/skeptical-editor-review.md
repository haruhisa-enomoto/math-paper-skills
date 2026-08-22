# Skeptical-editor review

Read this guide before running or supervising a skeptical-editor review of a
mathematics manuscript.  This is an independent whole-manuscript exposition
audit.  It asks a different question from a forward-blind first reading:

> Having understood the complete paper, what would an intended reader lose if
> this passage were deleted?

Truth, grammatical clarity, and a reconstructible purpose are necessary but
not sufficient reasons to retain prose.  The editor tests marginal reader
value without treating shortness as an end in itself. Apply the
[mathematical paper-writing guide](../../write-research-paper/references/paper-writing.md)
throughout the review.

## When to run one

Run this pass on the nearly final integrated revision of:

- a new paper;
- a whole-manuscript exposition revision; or
- a substantial addition that changes the paper's promise, architecture, or
  length and detail budget.

Also run it when the owner requests compression or raises recurring concerns
about disclaimers, repeated explanation, informal aliases, or apparently
coined result names.  It is not routinely required for a precise local repair
which adds none of those risks.

This pass does not replace continuous first reading or post-edit regression:

```text
continuous reader  -> can the paper be followed on first encounter?
skeptical editor   -> does each retained passage repay its cost?
delta regression  -> did accepted edits preserve local readability?
```

## Valid-run requirements

A valid run requires all of the following:

1. **Fresh editor.** Use a subagent with no inherited writer conversation,
   diagnoses, research state, or earlier review.  The writer or supervisor
   must not perform this role.
2. **Frozen complete paper.** Identify one exact manuscript revision and a
   content hash for the complete reading-order copy. Give the editor that copy
   only after initialization; before reading, the editor recomputes the hash by
   the recorded method and stops if it differs.
3. **Explicit contract.** State the intended audience, paper promise, length
   and detail boundary, protected content, allowed files, withheld material,
   and report destination without naming suspected defects or desired cuts.
4. **Read-only manuscript.** The editor writes only its report and never edits
   the manuscript.
5. **Isolation.** Withhold proof notes, ledgers, cited sources, vocabulary
   reports, drafting history, prior reviews, proposed repairs, and owner gold.

If freshness, frozen input, or read-only isolation fails, mark the run invalid.

## Setup and launch

Create a temporary review directory under the host project's ordinary scratch
policy. Flatten a multi-file manuscript into reading order when necessary and
preserve source locators. Copy and fill the writer skill's
[skeptical-editor direction](../../write-research-paper/assets/skeptical-editor-direction.md)
and [skeptical-editor launcher](../../write-research-paper/assets/skeptical-editor-launcher.md)
templates.

Launch in two steps.  First give a fresh agent only `DIRECTION.md` and the
guides it names.  Wait for confirmation that the guides are loaded and no
manuscript has been opened.  Then give that same editor the complete frozen
reading copy.  Do not add diagnoses, target phrases, or reactions while the
run is active.

Unlike a continuous first-reader relay, this editor must see the complete
paper.  Redundancy, displaced explanation, and unnecessary qualifications can
only be judged against the whole argument.

## Reading protocol

The editor makes two passes.

1. **Recover the paper.** Read once in order and record the paper's promise,
   result hierarchy, section jobs, intended audience, and apparent length and
   detail boundary.  Do not begin by hunting for trigger words.
2. **Apply the deletion counterfactual.** Read again and test the marginal
   contribution of each paragraph, with particular attention to transitions,
   remarks, qualifications, negative scope statements, repeated explanations,
   informal aliases, descriptive adjectives, and phrases shaped like names of
   theorems or criteria.

For a candidate passage ask:

- What exact reader-visible loss follows from deletion?
- Which intended reader benefits, and from what confusion or missing
  capability are they protected?
- Is the same information already available from a theorem statement,
  notation, proof, citation, or earlier paragraph?
- Does the passage explain mathematics, or does it defend the author's scope,
  method, or wording against an objection the paper has not raised?
- Does an informal label genuinely reduce later reading work?
- Is an apparent theorem name conventional, explicitly introduced, or merely
  a descriptive phrase made to sound established?

A passage normally earns retention when it prevents a plausible false
inference, explains an otherwise puzzling hypothesis, distinguishes the new
result from nearby work, exposes a proof dependency, supplies context needed
for a later argument, or materially helps the intended reader use the result.
Being true, clear, harmless, or mathematically related is not by itself enough.

Do not optimize raw word count.  Keep necessary hypotheses, definitions,
motivation, proof explanations, and scope boundaries.  Do not replace correct
technical terminology merely because it is specialized.  This is exposition
review, not proof verification, source checking, novelty assessment, or copy
editing.

## Finding categories

- `[delete]` -- deletion causes no identifiable reader-visible loss.
- `[compress]` -- useful content occupies disproportionate space or repeats
  material that can be stated once.
- `[label]` -- an informal alias or metaphor adds terminology without reducing
  later work.
- `[name]` -- wording suggests a conventional theorem, criterion, or principle
  without establishing that name or giving an immediate referent.
- `[defensive]` -- a qualification answers no plausible question raised by the
  paper or protects the writer's choice rather than the reader's understanding.
- `[repeat]` -- the same mathematical work has already been done elsewhere in
  the paper without a new local role.

Do not infer a defect from a keyword alone.  State the passage's intended role
and the deletion counterfactual before assigning a category.  A brief repair
direction is allowed, but the editor does not rewrite the manuscript.

## Report

The report records mode, exact revision, material read, isolation conditions,
verified reading-copy identity, and completion state.  It then contains:

1. **Recovered contract:** the promise, audience, result hierarchy, section
   jobs, and apparent detail budget learned from the manuscript and direction.
2. **Section audit:** for every section, whether it earns its place and any
   recurring source of excess or avoidable terminology.
3. **Mandatory inventories:** every explicit remark; every negative or
   defensive scope qualification; every recurring informal alias; and every
   phrase presented as a named theorem, criterion, principle, method, or
   argument.  Give each a `keep`, `compress`, `delete`, or `rename` verdict and
   one sentence identifying the reader benefit or its absence.
4. **Findings:** ranked findings with the quoted opening phrase, locator,
   category, intended role, exact reader-visible loss under deletion, concrete
   beneficiary if any, verdict, and confidence.
5. **Verdict:** whether the manuscript passes the necessity audit, and which
   findings involve objective exposition defects rather than choices about
   voice, historical context, or paper scope.

Silence is not endorsement.  A passed editorial review does not certify proof
correctness, source accuracy, novelty, or first-encounter readability.

## Adjudication and regression

The writer reads the complete report and adjudicates it; the editor has no edit
authority.  Undefined aliases, apparently coined result names, literal
repetition, and qualifications with no reader-visible payoff are usually local
exposition defects.  Removing substantial context, history, comparisons, or
owner-approved scope discussion may require owner judgment.

Apply accepted findings as one bounded revision.  Ordinary deletions,
compressions, and renamings then receive fresh delta regression.  If the edits
change the paper promise, structural front matter, section order, or reading
path, run a new continuous review instead.  Substantial replacement prose, new
remarks, or new qualifications require another skeptical-editor pass; a clean
deletion does not.
