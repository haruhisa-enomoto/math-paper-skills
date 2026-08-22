# Skeptical-editor review: direction

<!--
TEMPLATE. Fill every {{ }} slot and delete these comments. Use with the
`read-research-paper` skill in `editorial` mode. Keep LAUNCHER.md separate; it is for the
supervisor and may contain the complete manuscript path before initialization.
-->

This document is the complete task instruction for a skeptical-editor review
of {{PAPER}}.  This is exposition-review work, not mathematical research.  Do
not load the project's mathematical boot state.

Before receiving manuscript text, activate `read-research-paper` in
`editorial` mode and read its `SKILL.md`, the portable paper-writing guide, and
the skeptical-editor protocol completely. Confirm readiness and wait; do not
open the manuscript before that exchange.

## Frozen contract

- Manuscript revision: {{EXACT_REVISION}}
- Frozen reading-copy identity and verification method:
  {{CONTENT_HASH_AND_COMMAND, for example a git hash-object or SHA-256 value}}
- Intended audience: {{AUDIENCE_AND_ASSUMED_BACKGROUND}}
- Paper promise: {{ONE_SENTENCE_PROMISE}}
- Length and detail boundary: {{APPROVED_BUDGET_OR_CONCISION_STANDARD}}
- Protected content and non-scope: {{LOCKS}}
- Report destination: {{REPORT_PATH}}

These items define the audit; they do not identify suspected defects or desired
conclusions.

## Role

Read the complete paper once to recover its promise, result hierarchy, section
jobs, and expository budget.  Then read it again as a skeptical editor.  For
each candidate passage ask:

> What exact reader-visible loss would result if this were deleted?

Understanding a passage's purpose does not prove that the purpose is worth the
reader's time.  Truth, clarity, mathematical relevance, and harmlessness are
not sufficient retention tests.  Conversely, do not shorten the paper at the
expense of necessary motivation, definitions, hypotheses, proof explanation,
or a genuinely useful scope boundary.

Pay particular attention to transitions, remarks, qualifications, negative
scope statements, repetition, informal aliases, evaluative adjectives, and
phrases that sound like names of theorems, criteria, principles, methods, or
arguments.  Do not flag a word or category by itself; explain its marginal
reader value.

## Isolation and authority

- Read only this direction, the reader skill and portable guides named above, the
  complete frozen manuscript supplied after initialization, and the report you
  write.
- Do not read {{WITHHELD_MATERIAL: proof notes, ledgers, sources, vocabulary
  reports, drafting history, earlier reviews, proposed repairs, compiled
  output, and owner discussion}}.
- Do not open cited sources or search for them.
- Do not verify proofs, citations, or novelty.
- Do not compile or edit the manuscript.
- Do not infer authority to revise from the requested review.

Before reading, recompute the supplied manuscript's content hash by the
recorded method and compare it with the frozen reading-copy identity. Do not
replace this check by a packet-level consistency statement. If it differs, if
the supplied manuscript does not match the recorded revision, or if you have
seen withheld material, mark the run invalid and stop.

## Categories

- `[delete]` -- no identifiable reader-visible loss under deletion.
- `[compress]` -- useful content takes disproportionate space or repeats.
- `[label]` -- an informal alias adds terminology without later benefit.
- `[name]` -- a result phrase sounds established without a conventional or
  immediately introduced referent.
- `[defensive]` -- a qualification answers no plausible question raised by the
  paper.
- `[repeat]` -- the same mathematical work has already been done without a new
  local role.

## Report

Write one Markdown report to the recorded destination.  Include:

1. mode, exact revision, verified reading-copy identity, material read,
   isolation conditions, and completion;
2. the recovered paper contract;
3. a section-by-section necessity audit;
4. inventories of every explicit remark, negative or defensive scope
   qualification, recurring informal alias, and named-result phrase, each with
   a `keep`, `compress`, `delete`, or `rename` verdict and one-sentence reason;
5. ranked findings giving the opening phrase, locator, category, intended role,
   reader-visible loss under deletion, concrete beneficiary if any, verdict,
   confidence, and at most a brief repair direction; and
6. an overall pass/fail verdict which distinguishes objective exposition
   defects from owner-judgment questions.

Do not rewrite passages.  Silence is not endorsement, and this review does not
certify mathematics, sources, novelty, or first-pass readability.
