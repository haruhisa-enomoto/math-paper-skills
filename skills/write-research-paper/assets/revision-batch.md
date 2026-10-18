# Revision batch: {{PAPER}}

Base reviewed revision: {{REVISION}}
Prepared: {{OS_TIMESTAMP}} by {{AGENT}}

## Source reviews

Copy verdicts literally. A writer does not infer `PASS` after making repairs.

| Review ID | Mode | Artifact | Exact reviewed revision | Literal verdict |
|---|---|---|---|---|
| | continuous | | | PASS \| FAIL \| INVALID |

## Finding coverage

Include every ranked finding, every distinct objective defect separately
stated in a synthesis, and every actionable editorial inventory item. Several
rows may map to one common-cause cluster. Do not make one cluster per journal
flag.

| Source finding ID | Evidence locator or journal entries | Cluster ID | Burden | Repair | Closure evidence |
|---|---|---|---|---|---|
| | | | accepted \| rejected \| deferred | reader's \| alternative: ... | |

Every source finding ID appears exactly once. A `rejected` burden requires
exact textual or audience-contract evidence about the burden, not about the
reader's proposed repair. An accepted burden needs changed text at its
locator. `Deferred` is open and prevents a finished checkpoint unless the
owner explicitly excludes it. Before finishing, verify that there are no
orphan, duplicate, or open source findings.

Use one cluster entry per common cause, not per flag or sentence.

## {{CLUSTER_ID}}: {{SHORT_CAUSE}}

Source finding IDs:

Observed stumble and exact locator:

Intended role and reader-visible loss under deletion, if editorial:

Concrete beneficiary, if any:

Intended exact referent or predicate and current reconstruction burden, if
editorial precision:

Likely common cause:

Cold-reader success test:

Reader's proposed repair, if any:

Burden: accepted | rejected | deferred

Burden evidence, mandatory for rejected or deferred:

Chosen repair, for an accepted burden: reader's | alternative (move | inline |
merge | rewrite | delete | other), with the reason; name any rule that bars the
reader's repair:

Explicit non-scope:

Risk: local/objective | owner-judgment (an edit to the wording of a recorded
owner choice is owner judgment)

Recommendation and tradeoff:

Changed locators:

Net prose change, if substantial:

Regression mode and covered cluster IDs:

Regression result, report, and checked revision:
