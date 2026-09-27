# Mathematical exposition standard

Read this standard for every writing or exposition-review task. It governs
reader-facing mathematics; the writer workflow and reader protocols govern
authorization, review coverage, and completion. Host instructions add local
conventions. Writers read the [paper-writing guide](paper-writing.md) in
full before editing; readers consult it only for the relevant topic when a
distinction below needs illustration or style calibration.

## Reader and purpose

Respect the requested repair boundary. If only one sentence creates the
identified dependency, repair that sentence without polishing the surrounding
section. For a request to make text independent of an accompanying package,
remove package-dependent prose while retaining the mathematical procedure,
scope, and reproducibility conditions already stated; do not substitute code,
pseudocode, or a reproduction command. A public verification reference can
remain when it serves the requested deliverable rather than replacing it.

Write for the stated mathematical audience without assuming access to private
discussion, research records, or cited sources. At each point use only what
that audience knows and the manuscript has already supplied. Expert
guessability and a successful proof audit do not establish readable exposition.

Every passage must contribute mathematics, motivation, necessary context, or
reproducibility information. For transitions, remarks, qualifications, repeated
explanations, informal aliases, and apparent result names, ask what exact
reader-visible loss deletion would cause. Truth and clarity alone do not earn
space. Preserve useful scope boundaries and optional interpretations, placing
the latter after the mathematics they interpret.

Private conversation controls the work, not the paper's narrative. If a passage
would be unnecessary had the same result been obtained without that conversation,
remove it and repair surrounding transitions. Removing process vocabulary alone
does not repair a passage whose purpose still comes from drafting history.
Use only authorship metadata authorized for this manuscript; follow the host's
placeholder or omission convention when none is supplied.

## Exact mathematical language

Give each substantive statement an exact subject, predicate, evidence status,
and immediate referent. State the membership, vanishing, factorization, equality,
or other condition actually used; an informal gloss may explain it but cannot
replace it. A later display does not repair an earlier opaque sentence.
Repeat notation or use a numbered reference when a relative pointer requires
backtracking. When a result, equation, or case already has a number, cite the
number rather than a descriptive label such as "the X formula" or "the
equality case", and number any display that a later sentence needs instead of
pointing to it by position. Distinguish new, imported, conditional, computed, and conjectural
statements where confusion is possible.

Define paper-specific terms, symbols, statistics, and constructions before use,
subject to the introduction rules below. Recall standard terms when conventions
vary or the assumed audience needs the precise meaning. Typography and adjectives
such as "canonical" do not define objects: state the construction or property.
State field, algebra, module-side, and other assumptions wherever load-bearing.

Use one established term per notion. Retain a new name or symbol only when it
names a useful mathematical object or materially reduces later reading work;
do not add near-synonyms or aliases for brief local expressions. Keep temporary
notation local. Put lasting notions in numbered Definitions, assignments with
input, output, and choice dependence in Constructions, and short local reminders
in prose. Prove well-definedness at the appropriate point. Cite imported
definitions precisely, separating their content from new conventions or
specializations; combine Definition--Proposition only when it improves the logic.
If a term depends on choosing representatives or auxiliary objects, make clear
which data it records and why that data is independent of the choices. State
and cite needed uniqueness or well-definedness input without inventing a source
locator or expanding a bounded definition repair into its proof.

Use familiar mathematical syntax and connectives without forced variation or
forced "we". Expose omitted operations and reasons when the intended reader
would otherwise reconstruct them; do not expand immediate routine steps.
Non-human subjects, passive voice, or particular words are not defects by
themselves. Calibrate style from complete approved passages, not frequency
counts or generalizations about an author's whole output.

## Organization and first encounters

The abstract must stand alone for its audience: setting, problem, and principal
results, without unexplained machinery, defensive commentary, or drafting history.
Keep abstracts within **150 words by default**, unless explicit owner or venue
instructions call for a different length. Check the word count when drafting or
revising an abstract. Leave secondary results and organizational detail to the
introduction rather than compressing every contribution into the abstract.

The introduction gives the governing question, precise principal results,
contribution relative to known work, and the main ideas needed to understand
the approach. Keep proof details in the body.

In the introduction, ordinary background vocabulary and harmless global
conventions may precede the closing conventions block. Define paper-specific
terms needed to understand an introductory theorem, and state any convention
whose choice changes a current assertion or formula. Elsewhere in the
introduction, describe a paper-specific term in ordinary language or omit it;
a later-section pointer is not a definition. The body still owes the complete
definition before using it. Apply ordinary first-use discipline strictly after
the introduction.

Close the introduction with separate bold unnumbered **Organization** and
**Conventions and notation** blocks, in that order. The first explains the
logical route; the second collects global setup without proof or motivation.
Do not interrupt the introductory narrative with harmless routine conventions.

Every numbered section and subsection, including appendices, begins with
ordinary prose before a formal environment, display, list, or nested heading.
Separately test the local handoff: what work just ended, what begins, and why
it belongs here. A generic roadmap can satisfy prose-first while still failing
continuity; a distant Organization block does not supply a missing local bridge.
No paragraph template is mandatory.

Headings identify the mathematical object and the work performed, in natural
grammatical form. Read the contents as a mathematical synopsis and avoid imposing
one repeated syntactic template. Give useful examples before or alongside
constructions when needed to understand them. Keep the conceptual argument in
the main text; move interruptive calculation to appendices with its role stated.

## Page layout

Leave page spacing and page breaks to the document class and LaTeX unless the
owner explicitly requests manual layout adjustments. Do not insert or tune
page breaks, page-height overrides, vertical spacing, margins, or similar
pagination controls to improve the appearance of a draft. Examples include
`\newpage`, `\clearpage`, `\enlargethispage`, and layout-driven `\vspace`.
Preserve owner-approved formatting. A request to revise prose, compile, or
inspect rendered pages does not by itself authorize layout adjustments.

## Statements, proofs, and sources

Explain why a formal statement appears in preceding prose. Avoid advertising
captions and coined theorem names; use established names or deliberately defined
ones. State objects, hypotheses, and conclusions so the result is locally
understandable. Mirror numbered parts in proofs; label implication directions
explicitly with a colon and explain appeals to duality or earlier parts.
Distinguish fixed-algebra implications from universal ones, including changes
of algebra along the argument.

Expose load-bearing calculations, constructions, and dependencies. Use Steps
for sequential stages, Cases for branches, Claims for local reusable assertions,
and Parts for statement parts. Announce a stepped proof, number only multiple
units, and attach the assertion or case condition immediately. Prefer short
transitions for a linear proof; avoid claims used only in the next sentence.
Steps normally continue the surrounding proof without separate proof endings;
local lemma-like claims may have their own proof. Do not repeat a reduction
after establishing its hypotheses.
When a conclusion precedes its justification, move it to the point where that
justification ends and state only the established intermediate result earlier.
Preserve both the conclusion and the existing proof order.

Consider a commutative diagram when several maps or universal properties would
otherwise require reconstruction. Label maps and identify the kernel, image,
or universal property used.

State the exact imported result, hypotheses, conventions, and source locator,
then distinguish the new application or specialization. State the restricted
or numerical consequence actually needed. A citation, author's name, named
classification, or invented possessive theorem label cannot substitute for its
mathematical content.

For computation, give exact finite scope and conventions; do not extrapolate
to a universal theorem. Give a computational counterexample explicitly enough
to verify and cite its certificate. Required review and artifact checks are
specified by the workflow; compilation alone does not certify exposition.
