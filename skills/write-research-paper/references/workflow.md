# Mathematics-paper workflow

This is the operational contract for the writer/supervisor. The portable
[paper-writing guide](paper-writing.md) is the exposition standard, while the
reader skill owns the independent review protocols. Host-project instructions
may add local state, tooling, artifact, and publication requirements.

## Owner intent, state, and authority

Keep one compact live writing state in the paper workspace. It records current
positive decisions, the manuscript base revision, valid gates, and the next
authorized action—not the history of every correction.

Infer a compact task contract from ordinary owner language:

- exact target and revision;
- requested outcome;
- whole-paper, named-section, or bounded edit scope;
- content boundary and structural locks;
- owner-decision boundary; and
- finish state.

Use read-only project inspection to resolve obvious details. If one material
axis remains ambiguous, ask one short question about that axis and wait. Do not
ask the owner to configure the harness, and never silently reduce a broad paper
task to one local repair.

`Edit authority` is exact:

- `none`: discuss, diagnose, review, or propose; do not edit the manuscript;
- a named file, section, or batch: edit only that scope; and
- a broad drafting request: draft within the current owner locks, without
  expanding the mathematical or publication target.

Skill activation never creates authority. Pause when a needed choice would
materially change the owner's audience, story, theorem hierarchy, scope, or
voice.

Treat owner wording as approved copy only when it is offered as copy. If the
owner marks a phrase as approximate, says an earlier version existed, or is
uncertain about the wording, recover the referenced text when available. If it
cannot be recovered, preserve the substantive direction but label new wording
as a proposal; do not silently literalize the paraphrase or invent a label.

## Route the task

Use the owner request, not the easiest defect found, to select a route:

```text
whole paper: freeze/continuous read -> objective repairs -> editorial read -> adjudicate/revise -> regress -> validate/finish
named section: cumulative read through section -> scoped revise -> regress -> validate/finish
exact local edit: revise -> delta regression -> validate/finish
new paper: shape -> draft/integrate -> continuous read -> objective repairs -> editorial read -> adjudicate/revise -> regress -> validate/finish
new section: shape if needed -> draft/integrate -> continuous read -> editorial read if promise/architecture/budget changes -> adjudicate/revise -> regress -> validate/finish
```

An unqualified request to revise a paper means the whole-paper route and
requires a new continuous read before editing. Do not substitute an existing
review unless the owner explicitly requests it. For a named-section task, the
reader receives the cumulative prefix through that section, while edit
authority remains confined to the section. A needed change outside that scope
requires one short expansion request.

A precise local correction may enter at `revise`, but it may not skip fresh
delta regression. Adding a section authorizes only the new section and the
minimal introduction, transition, cross-reference, and later-summary changes
needed to integrate it. Reopen shape before a new paper or any addition that
materially changes audience, promise, result package, architecture, or budget.

### Shape calibration

Before full drafting, present one owner decision bundle containing:

- audience and assumed background;
- one-sentence paper promise;
- three to five results in narrative order;
- section jobs and alternate reading paths;
- main-text/appendix and length/detail boundary; and
- provisional title, abstract/introduction sketch, and one representative body
  passage.

Record approved choices positively with locators or exemplars. Reopen shape
only after a material change to audience, promise, result package,
architecture, or budget. Title wording may remain provisional.

The default workflow has two planned owner batches: this calibration and the
post-review adjudication batch. Ask between them only for a genuinely blocking
owner choice, not routine section approval.

### Draft and integrate

Draft section-sized units within the locks. Before writing a section, know what
the reader may use, what capability the section adds, why it appears there,
and what later result consumes it.

Integrate in document order. Check first encounters, terminology, theorem
hierarchy, reading paths, duplicated explanation, orphaned remarks, and unused
machinery. Record the exact revision and audit scope. This contaminated
writer-side pass is not independent reading evidence. Never label it forward
reading, forward-blind reading, or a cold review.

Apply two tests to every transition, remark, qualification, repeated
explanation, informal alias, and apparent result name. First, retain it only
when deletion would cause an identifiable loss for the intended reader, such
as a plausible false inference, an unexplained hypothesis, a hidden dependency,
or missing context used later. Second, if retained, require an exact
mathematical subject, predicate, status, and referent. A true limitation or
understandable purpose does not by itself earn space, and a reader's ability to
guess which theorem or assertion was intended does not make the wording
precise.

### Freeze and review

Freeze one revision. The host must give `read-research-paper` a fresh,
read-only context without drafting history, expected findings, owner gold, or
later manuscript text. One stable reader must handle a continuous review; use
another fresh reader for delta regression. Do not default to a swarm.

Use a two-step launch: first give the fresh reader only the governing guides
and task direction and wait for its readiness confirmation; then reveal the
first cumulative segment. Never combine initialization and manuscript exposure
in one message.

If isolation, frozen input, or reader continuity cannot be established, record
the review as invalid rather than weakening the label.

### Run the skeptical editorial pass

After the continuous report, apply only clear local/objective repairs needed to
produce a coherent integrated candidate; defer owner-judgment findings. For a
new paper or whole-manuscript revision, freeze that candidate and run a fresh
agent in `editorial` mode under the reader skill's
[skeptical-editor protocol](../../read-research-paper/references/skeptical-editor-review.md).
Also run the pass for a substantial addition that changes the promise, architecture, or
length and detail budget, and whenever the owner specifically requests a
necessity, compression, or referential-precision audit.

The editor receives the complete reading-order manuscript with a reproducible
content hash, audience, promise, detail budget, and protected content, but no
drafting history, diagnoses, continuous report, vocabulary report, owner gold,
or proposed cuts. It verifies the hash before reading, reads the whole paper,
then runs separate necessity and referential-precision audits. It inventories
remarks, defensive qualifications, informal aliases, apparent result names,
loose result pointers, and descriptive substitutes for exact mathematical
predicates. A necessity finding must identify marginal reader value rather
than merely say that a passage is clear or mathematically true. A precision
finding must identify the intended exact referent or predicate and the
inference or ambiguity imposed by the current wording; a necessary passage may
require `rename` or `replace` rather than deletion or compression.

Continuous and editorial reports form one review cycle. Adjudicate their
owner-judgment findings together. Accepted clean deletions, compressions,
renamings, and local precision replacements need ordinary final regression,
not another editorial pass.
Substantial replacement prose, new remarks, or new qualifications invalidate
the editorial gate and require another fresh editorial review.

### Adjudicate and revise

Read the complete review before editing. Convert observations into clusters by
common cause. Each cluster records an exact stumble, success test, minimal
repair, explicit non-scope, risk class, decision, changed locators, and
regression result.

First decide whether the evidence establishes a defect at all. Abstention is a
valid decision. Missing surrounding context warrants a conditional diagnosis,
not a manufactured repair.

`local/objective` means the intended result is fixed by accepted manuscript
content or an accepted project convention—for example, a broken reference, undefined
symbol, literal numerical error, omitted already-accepted hypothesis, or clear
drafting-process leakage with a direct deletion or replacement.

`owner-judgment` includes paper promise, story or architecture, title/abstract
voice, theorem hierarchy, literature position, length/detail boundary,
retention of substantial material, new terminology, and disputed diagnoses.
Batch these with one recommendation, reason, tradeoff, and minimal alternative.

A reader's prescription is not an accepted repair. Use the smallest repair
that passes the cold-reader success test:

1. delete unneeded material;
2. reorder existing material;
3. replace the defective sentence or paragraph;
4. add one local clause; then
5. add a definition, proof block, or theory only if the interface requires it.

Apply accepted clusters in one bounded pass. Check the aggregate diff against
success tests and non-scopes, and justify substantial net prose growth. For an
editorial necessity finding, record the passage's intended role, the exact
reader-visible loss under deletion, and any concrete beneficiary before
deciding to retain it. For an editorial precision finding, record the intended
exact referent or predicate, what the current wording licenses, and the
reconstruction imposed on the reader before deciding to keep, rename, or
replace it.

### Adjudicate host-project diagnostics

After applying the accepted revision and before freezing it for independent
regression, run any writer-side diagnostics required by the host project. A
diagnostic locates passages for judgment; its warnings are not defects and
clearing its warning count is not a success criterion.

For a lexical or terminology warning, inspect the complete sentence and its
mathematical role before changing the flagged form. Decide first whether the
passage uses an undefined or unnecessary label, an ordinary-language
paraphrase that hides the exact mathematical predicate, an apparent theorem
name without an established referent, a citation in place of the result being
used, or private-process language. Repair that semantic or expository defect
under the paper-writing guide. Consider spelling, hyphenation, or another
surface normalization only after the phrase itself is precise, necessary, and
properly introduced.

Never change a token merely to make a warning disappear. A justified technical
term may remain flagged. The diagnostic gate is satisfied when the required
scope has been checked against the exact revision and every warning has been
inspected and adjudicated, not when the report is empty. Rerun the diagnostic
after any accepted wording change so that the recorded report matches the
revision being frozen. Keep writer-side diagnostic reports from isolated
readers.

### Regress, validate, and finish

A fresh delta reader checks changed regions, surrounding context, and recorded
success tests without seeing diagnoses or preferred repairs.

Independent regression is a completion invariant for every exposition edit,
including a local objective or writer-found repair. Freeze the changed revision
and run delta regression unless the change invalidates the continuous review,
in which case run a new continuous review. Do not report the revision complete
or create its finished project checkpoint before the required gate passes. A
pre-edit review cannot certify the repair. Only an explicit owner
waiver for the named edit may bypass this gate; record and report the waiver.
If a suitable fresh reader is unavailable, leave the revision unfinished and
report `revision drafted; independent regression pending`.

- Any further edit to a checked region or its dependency invalidates its delta
  result.
- A changed promise, structural front matter, section order, or reading path
  invalidates the continuous review and requires a new full run.
- Unchanged local prose outside those dependencies does not require a full run.

A completed writing task is tied to one exact revision. Require current shape
locks, all accepted clusters applied, the appropriate continuous and editorial
gates, final regression, compilation, and any artifact or checkpoint checks
required by the host project. If regression fails, repair
and run another fresh regression reader until it passes or owner input is
needed. If no repair is accepted, do not manufacture an edit or empty
checkpoint. Keep ordinary reader and editor reports in the host project's
temporary review area unless their preservation was authorized.

Do not prepare submission packages, declare a release, or perform external
publication actions unless the owner separately requests them. Compilation,
search results, automated checks, and writer self-review do not certify the
whole manuscript.
