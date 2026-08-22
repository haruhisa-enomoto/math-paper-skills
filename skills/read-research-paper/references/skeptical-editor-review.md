# Skeptical-editor review

Read this guide before running or supervising a skeptical-editor review of a
mathematics manuscript.  This is an independent whole-manuscript exposition
audit.  It asks different questions from a forward-blind first reading:

1. **Necessity:** Having understood the complete paper, what would an intended
   reader lose if this passage were deleted?
2. **Referential precision:** If the passage remains, can the reader identify
   its exact mathematical subject, predicate, status, and referent without
   guessing from context?

Truth, grammatical clarity, and a reconstructible purpose are necessary but
not sufficient reasons to retain prose or accept its wording.  The editor tests
marginal reader value without treating shortness as an end in itself, and it
tests the semantic interface of retained prose without turning the review into
copy editing. A passage may earn its space yet still require an exact theorem
reference, predicate, status marker, or replacement for an apparent result
name. Apply the
[mathematical paper-writing guide](../../write-research-paper/references/paper-writing.md)
throughout the review.

## When to run one

Run this pass on the nearly final integrated revision of:

- a new paper;
- a whole-manuscript exposition revision; or
- a substantial addition that changes the paper's promise, architecture, or
  length and detail budget.

Also run it when the owner requests compression or raises recurring concerns
about disclaimers, repeated explanation, informal aliases, apparently coined
result names, loose result pointers, or ordinary-language phrases that hide an
exact mathematical assertion.  It is not routinely required for a precise
local repair which adds none of those risks.

This pass does not replace continuous first reading or post-edit regression:

```text
continuous reader  -> can the paper be followed on first encounter?
skeptical editor   -> does each passage repay its cost and state its interface precisely?
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
paper.  Redundancy, displaced explanation, unnecessary qualifications, and the
uniqueness and consistency of result or object references can only be judged
against the whole argument.

## Reading protocol

The editor makes two passes.

1. **Recover the paper.** Read once in order and record the paper's promise,
   result hierarchy, section jobs, intended audience, and apparent length and
   detail boundary.  Do not begin by hunting for trigger words.
2. **Run the two editorial audits.** Read again and test both the marginal
   contribution and the referential precision of the prose, with particular
   attention to transitions, remarks, qualifications, negative scope
   statements, repeated explanations, informal aliases, descriptive
   adjectives, citations used as result pointers, ordinary-language
   substitutes for exact predicates, and phrases shaped like names of theorems
   or criteria.

### Introduction architecture

Audit the introduction under its specific contract in the paper-writing guide.
Do not classify standard background vocabulary or harmless conventional
notation as imprecise solely because the closing **Conventions and notation**
block has not yet appeared. Require a concrete ambiguity: the object is not
available to the stated audience, the terminology is paper-specific, or a
plausible choice of convention changes the current assertion or display. A
later block must not be used retroactively to excuse a genuine ambiguity in an
introductory theorem.

Treat the closing **Organization** and **Conventions and notation** blocks as
distinct structural components rather than presumptive repetition. Audit the
first for a concise account of the paper's logical route and the second for the
global setup needed by the body; flag either block when it is missing,
misplaced, merged with the other, substantively incomplete, or filled with
material belonging to the mathematical narrative. After the introduction,
apply the ordinary first-occurrence and referential-precision standards
strictly.

### Transitions and local handoffs

The continuous reader owns the first-encounter evidence about whether a
boundary feels abrupt. In this whole-paper pass, do not infer that experience
from hindsight. Instead, when auditing an existing transition, count a concise
local handoff as reader-visible work when it connects the task just completed
to the task now beginning, explains why a formal statement appears at that
point, or prevents an abrupt change of discourse mode. A global Organization
block does not automatically make such a local bridge repetitive. Conversely,
generic roadmap prose which supplies no distinct local capability does not earn
retention merely because it is transitional. Do not require every section to
have a prose preface when its heading and opening statement already perform the
handoff.

### Necessity audit

For a candidate passage ask:

- What exact reader-visible loss follows from deletion?
- Which intended reader benefits, and from what confusion or missing
  capability are they protected?
- Is the same information already available from a theorem statement,
  notation, proof, citation, or earlier paragraph?
- Does the passage explain mathematics, or does it defend the author's scope,
  method, or wording against an objection the paper has not raised?

A passage normally earns retention when it prevents a plausible false
inference, explains an otherwise puzzling hypothesis, distinguishes the new
result from nearby work, exposes a proof dependency, supplies context needed
for a later argument, or materially helps the intended reader use the result.
Being true, clear, harmless, or mathematically related is not by itself enough.

### Referential-precision audit

For retained mathematical work ask:

- Does each substantive sentence expose the exact subject and predicate, or
  does ordinary English leave the reader to infer a membership, containment,
  vanishing, factorization, implication, or other assertion?
- Does every pronoun, descriptive phrase, relative pointer, and citation-based
  application have one immediate mathematical referent?
- When a result is applied, does the prose identify the exact statement or
  numbered referent used, rather than asking the reader to know what a broad
  citation or descriptive label contains?
- Is an apparent theorem, criterion, principle, method, or argument name
  conventional, explicitly introduced, or immediately tied to an exact
  referent, rather than making a guessable application sound like an
  established name?
- Does an informal alias genuinely reduce later reading work, map uniquely to
  its mathematical object, and remain consistent throughout the paper?
- Is the evidence status visible—new, imported, conditional, computed, or
  conjectural—where a reasonable reader could otherwise misclassify it?

Record the inference or backward search required by the current wording. A
competent reader's ability to reconstruct the intended meaning does not make
the interface precise. A passage may pass the necessity audit and still require
`rename` or `replace`.

Do not optimize raw word count.  Keep necessary hypotheses, definitions,
motivation, proof explanations, and scope boundaries.  Do not replace correct
technical terminology merely because it is specialized.  This is exposition
review, not proof verification, source checking, novelty assessment, or copy
editing. The precision audit concerns mathematical reference and status, not a
reviewer's preferred prose style.

## Finding categories

- `[delete]` -- deletion causes no identifiable reader-visible loss.
- `[compress]` -- useful content occupies disproportionate space or repeats
  material that can be stated once.
- `[label]` -- an informal alias or metaphor adds terminology without reducing
  later work.
- `[name]` -- wording suggests a conventional theorem, criterion, or principle
  without establishing that name or giving an immediate referent.
- `[precision]` -- retained wording makes the exact object, predicate, result,
  citation interface, or evidence status recoverable only through guesswork or
  backward reconstruction.
- `[defensive]` -- a qualification answers no plausible question raised by the
  paper or protects the writer's choice rather than the reader's understanding.
- `[repeat]` -- the same mathematical work has already been done elsewhere in
  the paper without a new local role.

Do not infer a defect from a keyword alone. State the passage's intended role
and give the evidence required by the relevant audit. For a necessity finding,
state the deletion counterfactual and concrete beneficiary, if any. For a
precision finding, state the intended exact referent or predicate, what the
current wording actually licenses, and the inference or ambiguity imposed on
the reader. A brief repair direction is allowed, but the editor does not
rewrite the manuscript.

## Report

The report records mode, exact revision, material read, isolation conditions,
verified reading-copy identity, and completion state.  It then contains:

1. **Recovered contract:** the promise, audience, result hierarchy, section
   jobs, and apparent detail budget learned from the manuscript and direction.
2. **Section audit:** for every section, whether it earns its place and any
   recurring source of excess, avoidable terminology, or imprecise
   mathematical reference.
3. **Mandatory inventories:** every explicit remark; every negative or
   defensive scope qualification; every recurring informal alias; and every
   phrase presented as a named theorem, criterion, principle, method, or
   argument. Also inventory every loose result pointer, descriptive substitute
   for an exact mathematical predicate, or citation-based application found in
   the precision audit. Give each a `keep`, `compress`, `delete`, `rename`, or
   `replace` verdict and one sentence identifying either its reader benefit or
   its exact referential defect.
4. **Findings:** ranked findings with the quoted opening phrase, locator,
   category, intended role, audit evidence, verdict, confidence, and at most a
   brief repair direction. Necessity evidence records reader-visible loss under
   deletion and any concrete beneficiary; precision evidence records the exact
   intended referent or predicate and the reconstruction currently required.
5. **Verdict:** separately whether the manuscript passes the necessity audit
   and the referential-precision audit, followed by an overall editorial
   verdict and a distinction between objective exposition defects and choices
   about voice, historical context, or paper scope.

Silence is not endorsement.  A passed editorial review does not certify proof
correctness, source accuracy, novelty, or first-encounter readability.

## Adjudication and regression

The writer reads the complete report and adjudicates it; the editor has no edit
authority. Undefined aliases, apparently coined result names, loose result
pointers, citations standing in for the assertion used, hidden mathematical
predicates, literal repetition, and qualifications with no reader-visible
payoff are usually local exposition defects. Removing substantial context,
history, comparisons, or owner-approved scope discussion may require owner
judgment.

Apply accepted findings as one bounded revision.  Ordinary deletions,
compressions, renamings, and local precision replacements then receive fresh
delta regression. If the edits change the paper promise, structural front
matter, section order, or reading path, run a new continuous review instead.
Substantial replacement prose, new remarks, or new qualifications require
another skeptical-editor pass; a clean deletion or exact local replacement
does not.
