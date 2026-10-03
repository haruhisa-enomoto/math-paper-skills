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

```text
whole paper: freeze/continuous read -> objective repairs -> editorial read -> adjudicate/revise -> regress -> validate/finish
named section: cumulative read through section -> scoped revise -> regress -> validate/finish
exact local edit: revise -> delta regression -> validate/finish
new paper: shape -> draft/integrate -> continuous read -> objective repairs -> editorial read -> adjudicate/revise -> regress -> validate/finish
new section: shape if needed -> draft/integrate -> continuous read -> editorial read if promise/architecture/budget changes -> adjudicate/revise -> regress -> validate/finish
```

An unqualified paper revision follows the whole-paper route with a new
continuous read before editing; use an existing report only when the owner
requests it. A named-section review receives the cumulative prefix through
that section, but edits remain confined to the authorized scope. Request a
needed expansion once. Adding a section includes the minimal introduction,
transition, cross-reference, and later-summary edits needed to integrate it.
An exact local correction still requires fresh independent regression.

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

Freeze the reading copy, preserving source locators for flattened inputs.
Supervise fresh isolated readers under their mode-specific protocols. Continuous
reading retains one reader and staged cumulative exposure. Editorial reading
accepts one packet with instructions and the complete frozen paper. Withhold
writer history, owner discussion, previous reviews, vocabulary diagnostics,
expected findings, proposed repairs, and author's choices or review contracts
other than the audience. If the required isolation or continuity
cannot be established, report the review invalid.

After continuous reading, apply clear local/objective repairs to create a
coherent candidate and defer unresolved owner choices. New papers and whole-paper
revisions require a fresh editorial audit of that candidate. Also run it for a
substantial addition changing promise, architecture, or detail budget, or an
explicit necessity, compression, or referential-precision audit. Read both
reports and resolve any remaining owner choices together where practical.

## Exhaustive adjudication

Before editing from a report, read it completely and populate
[revision-batch.md](../assets/revision-batch.md). Preserve each literal source
verdict and exact revision. Map every ranked finding, separately stated
objective burden, and actionable editorial inventory item to exactly one
repair cluster; assign source IDs where missing. Repeated instances may share
one cause and cluster, but none may disappear. Journal entries support findings
and need not each become a cluster.

For each cluster record the observed burden, success criterion, minimal repair,
non-scope, risk, decision, changed locators, and regression evidence. Decide:

- `implement`: accept diagnosis and repair class;
- `modify`: accept the observed burden and choose another repair;
- `reject`: cite exact manuscript text or an explicit audience/owner contract
  showing why the reported burden is not a defect;
- `defer`: keep an unresolved decision or missing evidence open.

Do not erase observed inference, rereading, backward search, or translation to
an exact predicate merely because an expert can recover the intended meaning.
Disagreeing with proposed wording does not reject the observation. A missing
predicate or referent fixed by accepted mathematics is a local/objective defect,
as are broken references, undefined notation, omitted accepted hypotheses,
literal errors, and direct process-leakage repairs. A nondefect decision needs
concrete text already available at that point or an explicit audience contract.

Paper promise, architecture, title/abstract voice, theorem hierarchy, literature
position, substantial retention, new terminology, and disputed diagnoses can
require owner judgment. Resolve them within existing authority where settled;
otherwise present the recommendation, reason, tradeoff, and minimal alternative.
Missing context warrants a conditional diagnosis, not an invented repair.

Use the smallest adequate repair: deletion, reordering, replacement, or a local
clause before adding a definition, proof block, or theory. Apply accepted clusters
as one bounded pass and check success criteria, non-scopes, and aggregate growth.
After each repair, reread the whole enclosing section in reading order (for the
abstract or introduction, all of it), not only the changed sentence, and check
that the repair fits there. Prefer deletion or plain restatement to new
wording. Do not rewrite a passage that is already acceptable only because a
reviewer offers other wording.
For retained editorial material, record the role, loss under deletion, and
beneficiary; for precision findings, record exact referent or predicate, what
current wording licenses, and the reader's reconstruction burden.

## Host diagnostics and mandatory regression

After repairs and before freezing, run every required host diagnostic over its
required scope and adjudicate every warning at the exact revision. Warnings are
locations for judgment, not automatic defects. For terminology, judge meaning,
necessity, and introduction before spelling or hyphenation. Never change text
just to clear a flag. Rerun after wording changes; withhold diagnostics from
independent readers. Host-specific commands and report conventions belong in
the host overlay.

Every exposition edit, including exact local and writer-found repairs, requires
fresh independent regression before completion. Only an explicit owner waiver
for that named edit bypasses it; record and report the waiver. The authorized
edit includes authorization to launch its necessary fresh reader. If unavailable, report
`revision drafted; independent regression pending` and leave the task unfinished.

For bounded repairs use the [delta protocol](../../read-research-paper/references/delta-review.md):
changed regions, surrounding dependencies, cluster IDs, and neutral success
criteria without diagnoses or preferred wording. Compare the packet's covered
IDs with the revision batch before launch and with the returned report.
A delta closes only those implemented/modified clusters actually checked; it
cannot close omitted or deferred findings or certify unchanged text.

Review validity follows the changed dependencies:

- Further edits to a checked region or its dependencies invalidate its delta.
- Changes to promise, structural front matter, section order, or reading path
  require a new continuous review instead of delta alone.
- Substantial replacement prose, new remarks, qualifications, or informal
  labels, or changes to promise, architecture, or detail budget require a new
  editorial pass. Clean deletions, compressions, renamings, and exact local
  precision replacements need regression but do not alone require that pass.
- Unchanged text outside those dependencies does not require another full run.

Repair failed regression and use another fresh reader until it passes or an
owner dependency arises. If abstract/introduction growth continues across
rounds, reconsider the repair class before commissioning another reader.

## Finish at one exact revision

Require current locks, complete source-finding coverage without duplicate or
orphan IDs, no unresolved objective finding, and no deferral unless the owner
explicitly excludes it. All implemented/modified clusters must be applied and
closed by the appropriate fresh evidence. Preserve source `FAIL` verdicts;
record current closure separately rather than relabeling old reports. A change
invalidating a whole-paper gate needs a new review in that mode.

Compile and inspect the log, complete all host diagnostics and artifact gates,
and inspect the aggregate diff. Render only affected pages for a concrete
visual concern, such as a diagram, clipping, or unusual break. Create the
host-authorized checkpoint only after required gates pass. Keep review reports
in temporary storage unless durable preservation is authorized. Do not invent
an edit or empty checkpoint when no repair is accepted. Submission packages,
release declarations, and external publication require separate authority.
