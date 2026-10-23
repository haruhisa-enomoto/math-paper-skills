---
name: polish-math-prose
description: Rewrite AI-like mathematical prose and compressed proof presentations into natural mathematical English, or repair mathematical defects flagged by a post-polish audit. Use after structural and exposition reviews converge.
---

# Polish mathematical prose and proof presentation

Act as a mathematical prose editor and proof-presentation polisher. Infer edit
scope from the conversation; skill activation never grants manuscript-edit or
publication authority. Preserve settled owner choices and unrelated work.

This skill is designed for the second and third phases of a multi-model
mathematics paper workflow:

1. **Structure & exposition relay** (`write-research-paper` +
   `read-research-paper`): initial drafting and isolated `FR`/`SE` review
   relays establish the mathematical architecture, definitions, notation, and
   completeness.
2. **Natural math-English & proof-presentation rewrite** (`polish-math-prose`,
   `rewrite` mode): a fresh-eyes pass rewrites cumulative patch syntax,
   causative compression, telegraphic proof imperatives, and awkward proof
   presentations into natural `amsart` mathematical English, logging all
   substantive mathematical argument touches in `REVISION-NOTES.md`.
3. **Mathematical diff audit loop** (mathematical auditor <->
   `polish-math-prose`, `repair` mode): a logic-specialist model audits the
   `git diff` and `REVISION-NOTES.md` against the pre-polish baseline for subtle
   mathematical regressions, quantifier shifts, or dropped hypotheses, and the
   polisher repairs any flagged items until the audit is clean.

Before editing, read completely the
[AI mathematical writing anti-patterns guide](references/anti-patterns.md), the
shared [exposition standard](../write-research-paper/references/exposition-standard.md),
the writing guide's sections
[State the mathematics exactly](../write-research-paper/references/paper-writing.md#3-state-the-mathematics-exactly)
and
[Expose the logic of statements and proofs](../write-research-paper/references/paper-writing.md#5-expose-the-logic-of-statements-and-proofs),
and the host project's paper-writing overlay (such as `docs/PAPER-WRITING.md`)
if present.

## Mode 1: Fresh-eyes prose and presentation rewrite (`rewrite`)

Use this mode when asked to review and rewrite a manuscript (or named sections)
for natural mathematical English and clear proof presentation.

### 1. Read with fresh eyes (do not anchor on patch history)

Read the live `.tex` files in reading order as a human mathematician reading a
submitted preprint. **Do not** load prior `.research-scratch` review reports
(`FR-*`, `SE-*`, `DELTA-*`) or `REVISION-BATCH.md` unless the owner explicitly
asks you to inspect a specific record. Those files reflect iterative patch
negotiations and will anchor you to the very patch-accretion syntax you are
there to remove.

### 2. Rewrite sentences, paragraphs, and proof presentations freely

Do not limit yourself to minimal word-level substitutions when a sentence,
transition, or proof paragraph is syntactically unnatural or telegraphically
compressed. You have full freedom to:

- rewrite full sentences and reorganize paragraph flow so that premises,
  operations, and conclusions appear in a natural logical order;
- unpack compressed one-line deductions or streamline redundant intermediate
  expressions in a proof so that the mathematical mechanism is transparent;
- replace telegraphic imperative chains (`"Eliminate... Give... Reverse..."`)
  with connected first-person plural (`we`) narrative;
- eliminate inanimate agency and causative verb compression (`"Nilpotence
  writes..."`, `"Linear independence puts..."`, `"Irreducibility makes..."`,
  `"The table forces..."`, `"kills"`);
- replace internal project shorthand or stacked noun modifiers (`"projective
  labels"`, `"unshiftable output"`, `"Z is intended"`) with standard
  mathematical terminology and explicit formulas;
- clean up parenthetical lemma-number clutter in narrative overview sections,
  separate dense `Conventions and notation` walls of text into thematic
  paragraphs, and move mid-argument global convention interruptions to the
  conventions block; and
- structure multi-branch case analyses (`\emph{Case 1: ...}`) and multi-step
  proofs (`\textbf{Step 1: ...}`) with explicit signposts and exhaustion
  statements.

Natural mathematical English is not prose in place of mathematics. The two
writing-guide sections in the read list above are binding here:

- turn a prose paraphrase of a short condition back into notation (write
  "$x \in U$", not "x lies in the set U described above"), and display a list
  or set instead of narrating it;
- divide a long proof into steps, cases, or claims, even when no reviewer
  asked for it;
- open the proof of each numbered part with its label as a paragraph heading
  (`(1)`, or `(1) $\Rightarrow$ (2):`), in the statement's order. Never move a
  part label into a sentence (`For (2), ...`, `this proves (1)`), and convert
  such sentences you find into headed paragraphs.

### 3. Tell the story

Read the abstract and introduction as a reader deciding whether to read the
paper. If they do not carry a story (why the question matters, what the paper
answers, and what the reader will learn), rewrite them: reorder, merge, or
replace paragraphs freely so that the motivation comes first, the main
results stand out, and limitations come last. Section openings may be
rewritten the same way. Keep every theorem statement and hypothesis exact.

The story continues through the body: rewrite transitions between sections
and the motivation before key constructions or results so that the reader
always knows why the next step is taken. A transition should carry
mathematical content (what was just shown and what it is needed for), not
generic roadmap boilerplate.

Larger reorganization of the body (moving a result, merging or splitting
sections) is allowed when it clearly improves the reading. List each such
change under "Structural changes" in `REVISION-NOTES.md`.

### 4. Log substantive mathematical touches in `REVISION-NOTES.md`

Because a subsequent mathematical audit will verify your changes against the
pre-polish baseline, create or update `REVISION-NOTES.md` (in the manuscript
directory or owner-specified path) with:

1. **Summary of prose and organizational improvements** by section;
2. **Structural changes**, if any: every moved result and every merged,
   split, added, or removed section, with old and new locations; and
3. **Substantive mathematical and proof-presentation log**: an explicit list of
   every location (with file, theorem/lemma/proposition number, and line range)
   where you unpacked a proof step, reordered or combined deductions, rewrote a
   formula or sign convention, adjusted a quantifier or hypothesis, or
   simplified an argument, explaining briefly what changed and why.

This log allows the mathematical auditor to focus immediately on every place
where mathematical meaning could have shifted.

### 5. Preserve invariants and validate the build

- Preserve all `\label`, `\ref`, `\eqref`, and `\cite` keys and theorem/equation
  numbering unless the owner explicitly authorizes changing them.
- Never leak reviewer, prompt, or process language into the manuscript.
- Compile the manuscript using the host's build command and inspect the log to
  ensure zero LaTeX errors, no undefined references, and no unintended layout
  regressions. Run the host's vocabulary checker if required by the host
  overlay.

## Mode 2: Post-audit mathematical repair (`repair`)

Use this mode when a mathematical audit (or the owner) reports mathematical
regressions, missing edge cases, quantifier or hypothesis shifts, or sign/index
discrepancies in your rewrite diff.

1. **Verify the mathematical requirement:** Read the auditor's finding and
   inspect the surrounding definitions, lemma statements, and proof steps to
   understand the exact mathematical constraint.
2. **Repair without reverting to robotic prose:** Fix the mathematical defect
   precisely and completely, but weave the correction into natural, readable
   mathematical English rather than wedging in a compressed parenthetical patch.
3. **Update `REVISION-NOTES.md`:** Append a post-audit repair section recording
   each flagged defect, the exact locator, and how the repair resolves it.
4. **Compile and verify:** Recompile the manuscript and confirm a clean build
   and clean diff before returning for re-audit.
