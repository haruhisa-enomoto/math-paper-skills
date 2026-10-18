# Finding ledger and gate evidence

The ledger lets the coordinator see repeats, repair-induced findings, and
churn across rounds. It never removes a finding from the writer's view and
never replaces the writer's adjudication.

## Ledger entries

After each review round and the writer's revision, add one row per source
finding, taken from the reports and the writer's revision batch:

| Field | Content |
|---|---|
| ID | source finding ID (for example `R3-FR-4`) |
| Locator | section and a short quoted anchor of the passage |
| Theme | a few words (for example "Bongartz chronology") |
| Burden | accepted, rejected, or deferred, copied literally from the revision batch |
| Repair | reader's or the named alternative, for an accepted burden |
| Risk | local/objective or owner judgment, from the revision batch |
| Class | see below |

Classes, assigned by the coordinator:

- **new**: no earlier entry with the same locator and theme;
- **repeat**: matches an earlier entry whose burden was rejected; record
  which;
- **repair failed**: matches an earlier entry whose burden was accepted and
  repaired, so the repair did not remove the burden;
- **repair-induced**: its locator lies in text changed by the previous
  revision (check with `git diff` between the two reviewed revisions);
- **lock**: asks to change a locked owner decision;
- **source access**: the burden exists only because the reader cannot open a
  cited source (an imported fact or a convention match). Once the writer
  states the import exactly, with locator and any change of convention,
  later repeats are tagged but do not count toward the three-reader
  escalation.

## Tags sent to the writer

For each repeat, repair failure, or lock finding, send one line under the
"Coordinator ledger tags (relay record, not owner direction)" label of the
revision prompt. State facts only: which earlier entry it matches and what
happened to it. Do not repeat the earlier reason as if it still settled the
matter, and do not propose a repair. For example:

```text
R7-FR-3 repeats R6-FR-7 (role of Lemma 2.2); round 6 rejected the burden under an owner style rule; the same burden is raised again.
R7-SE-2 matches R6-SE-5 (repeated intro claim); round 6 accepted the burden and repaired it; the burden is raised again.
```

Lock findings go to the writer only as information, not as items to act on.
Never tell readers what was rejected.

When the same rejected burden is raised by three independent readers, do
not tag it for another rejection: bring it to the owner at the next gate,
since the rejection may be wrong.

## Starting mid-relay

When no state file exists, rebuild the ledger and counts only for the
current structural version, from whatever records exist (reports, revision
batches, coverage tables). Mark rebuilt rows as rebuilt; do not invent
counts that the records do not support.

A revision starts a new **structural version** when it changes the paper
promise, a main theorem statement or its scope, the section order, or adds
or removes a section or appendix. Wording, proofs, examples, and remarks
within existing sections do not.

## Per-round metrics

After each writer revision, record in the state file:

- FR and SE finding counts and literal verdicts;
- counts by class: new objective, repeat, repair failed, repair-induced,
  lock, owner judgment;
- words in total, introduction, and abstract (`texcount`), counted the
  same way every round;
- passages edited in each of the last three revisions, from `git diff`
  hunks mapped to sections or paragraphs.

FR verdicts and counts stay high by design (a fresh forward reader always
reports some friction), so they are not a stopping test. SE counts and the
share of new objective findings are more informative, but the decision
belongs to the owner.

## Evidence table at a gate

```text
| Round | Revision | FR | SE | New objective | Repeat | Repair failed | Repair-induced | Words (total/intro/abstract) |
|-------|----------|----|----|---------------|--------|---------------|----------------|------------------------------|

Introduction and abstract length since the last gate: <words per round>

Churned passages (edited in 3 consecutive rounds, or text added then removed):
- <locator>: <round>: <what changed>, ...

Burdens raised by 3 readers after rejection:
- <theme>: <IDs>, writer's reason: ...

Accepted burdens raised again after repair:
- <theme>: <IDs>, repairs tried: ...

Open owner-judgment items and deferrals:
- ...

Changes since the last gate that the owner has not seen (scope, structure,
theorem statements):
- ...

Recommendation for the next step (not a convergence claim): ...
```

Keep the table short. Link the report files rather than quoting them.
