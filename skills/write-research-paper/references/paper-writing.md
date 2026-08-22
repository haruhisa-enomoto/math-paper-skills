# Mathematical paper writing

Read this guide end to end when the writing or reviewing skill directs you to
it; a bounded excerpt does not satisfy that step. It governs mathematical
exposition, not merely TeX syntax or PDF layout. A host project may add local
authorship, formatting, evidence, or publication conventions, but those local
rules do not replace this standard.

## Authorship metadata

Do not invent or infer an author's name, affiliation, address, email address,
or other identity metadata. Use only metadata authorized for the manuscript at
hand. If none is supplied, omit it or use an unmistakable placeholder according
to the requested deliverable and any host-project convention.

## 1. Write for a forward reader

Write for a mathematician who has the background explicitly assumed by the
paper but has not read the research ledger, internal proof notes, earlier agent
conversations, or the sources being cited. At each point, the reader may use
what the paper has already explained, but not a definition, motivation, or
example that appears later. Expert guessability is not sufficient: a successful
proof audit does not imply that the exposition passes this standard.

A section or subsection should open by saying, in ordinary mathematical
language, what will be studied and why it matters to the paper. Do not orient
the reader by listing technical consequences whose meaning has not yet been
introduced. A section that passes to a covering should first say which group
acts on which quiver, what the covering algebra is, and why the conjecture
under study transfers along the covering; terms such as `Galois covering`,
`push-down functor`, and `locally bounded category` must not carry the opening
explanation before the reader knows what they mean.

Read for continuity at major boundaries, not only for recoverability within
individual paragraphs. At a section or subsection break, keep active the
mathematical job that has just ended and inspect the heading together with the
first paragraph or formal statement. They should provide an adequate handoff:
why this task begins here, how it uses or departs from the preceding work, and
what immediate role it has in the argument. A closing Organization block may
make the global sequence reconstructible without making a later local handoff
feel natural.

Do not force every section to begin with a stock roadmap sentence. A theorem,
definition, or example may open a section when its heading and statement make
the connection immediate. Repair a boundary when the reader must silently
supply a change of task or discourse mode, wait for a later paragraph to learn
why the new material appeared, or treat an intervening technical block as an
interruption. Use the smallest mathematical bridge that supplies the missing
function, and do not merely repeat the table of contents.

There is no mandatory paragraph template. An order such as

```text
motivation -> definition -> statement -> proof -> interpretation
```

is one useful possibility, not a rule. The correct order depends on the
mathematics. The governing requirement is that every paragraph be
understandable where it occurs and that the reader know why it is there.

## 2. Keep the manuscript about mathematics

Every sentence should state mathematics, explain why some mathematics is being
introduced, or provide necessary mathematical context. Delete prose which
merely advertises, reassures, evaluates, or records the writer's process. A
genuine hypothesis or scope statement should instead be stated directly.

Drafting instructions govern revisions, not manuscript prose. Apply a requested
proof method or level of exposition without announcing the request or the
rejected alternative. Mention an alternative method only when the comparison
has mathematical content.

Drafting instruction:

> Prove that \(f\) is surjective from \(fg=1_Y\); do not invoke the separate
> injectivity argument.

Bad manuscript response:

> We prove surjectivity directly and do not use the injectivity of \(f\).

Better manuscript response:

> If \(g:Y\to X\) satisfies \(fg=1_Y\), then every \(y\in Y\) equals
> \(f(g(y))\). Hence \(f\) is surjective.

Bad:

> No knowledge of spectral sequences is assumed.

Better:

> Proposition 2.1 states the five-term exact sequence used in the proof.

Bad:

> The following striking result reveals a rich structure.

Better:

> The following theorem classifies the maximal subgroups of \(G\).

Do not copy the wording of an instruction, prompt, review criterion, revision
request, or private discussion into the manuscript. Do not tell the reader what
the author or an agent was asked to do, which defects a reader reported, or
which internal constraint shaped a paragraph. Such information belongs in
working records or correspondence.

This rule does not prohibit mathematical scope statements. A sentence such as
`The argument proves the split case but does not descend through a nonsplit
separable quotient` may convey a relevant mathematical boundary. Truth and
clarity alone do not make a qualification useful, however. Keep it only when
it prevents a plausible overreading, explains a hypothesis, distinguishes the
result from nearby work, or affects a later argument or application. If the
theorem statement already makes the boundary clear and the paper raises no
reason to discuss it, omit the qualification.

### Hard boundary: private discussion is not manuscript content

**Conversational salience is never a criterion for inclusion in a public
manuscript.** The conversation controls the work; it does not supply the
paper's narrative. Every sentence, paragraph, remark, implementation detail,
qualification, and comparison must earn its place independently through the
mathematics presented to the reader: the problem, result, proof, necessary
context, or genuine reproducibility requirements.

Apply a counterfactual test during drafting and revision: if the same
mathematical result and evidence had been obtained without the private
conversation, would the passage still be needed in this paper at this point?
If not, delete it. This test applies regardless of the subject or form of the
private exchange and regardless of whether its wording has been disguised as
ordinary mathematical prose.

Audit violations at the level of purpose, not vocabulary. Removing an explicit
process phrase is insufficient when the passage's reason for existing still
comes from the private discussion. After removing such a passage, inspect the
surrounding transitions and section structure as well, since they may preserve
the same leaked agenda implicitly.

## 3. State the mathematics exactly

A substantive sentence should identify its mathematical subject, state the
predicate being asserted, and give every pronoun or descriptive phrase an
immediate referent. Repeat an object or its notation when the reader would
otherwise have to search backward.

Bad:

> The first is contained in the second, so it is finite.

Better:

> Since \(X\subseteq Y\) and \(Y\) is finite, \(X\) is finite.

State the membership, containment, vanishing, factorization, injectivity,
surjectivity, or equality actually used. An informal description may follow an
exact statement when it helps, but should not replace it.

Bad:

> The element survives in the quotient.

Better:

> The coset \(x+N\) is nonzero in \(M/N\).

A technically available antecedent is not enough if recovering it requires
backtracking, remembering several objects, or noticing that the ambient algebra
or module category has changed. Avoid phrases such as `the two restricted
classes`, `the former map`, `the remaining term`, or `this group` unless the
referents are both immediate and unique, and state an equality such as

```text
\(\operatorname{Ext}^i_A(\Omega M,A)\cong\operatorname{Ext}^{i+1}_A(M,A)\)
for every \(i\ge 1\)
```

before summarizing its consequence. A display which appears only after an opaque
sentence does not make that sentence forward-readable.

When a sentence merely paraphrases a short mathematical condition, state the
condition in notation. Prefer

```text
Assume that \(\operatorname{Hom}_A(M,K)\ne 0\).
Choose an indecomposable direct summand \(Z\) of \(K\) such that
\(\operatorname{Hom}_A(M,Z)\ne 0\).
```

to idioms such as `K receives a nonzero map from M`. Avoid English-dependent
spatial or directional paraphrases which conceal a standard predicate:
expressions such as `the extension dies`, `the syzygy stabilizes`, `the module
survives the shift`, or `the map passes through the projectives` are useful
only when they have already been given a precise meaning and genuinely shorten
a repeated argument.

This is not a rule to replace mathematical prose by strings of symbols. Plain
mathematical language uses ordinary syntax to explain the logical movement and
the purpose of a construction, while stating load-bearing predicates exactly.
Here `plain` means conventional, low-friction mathematical prose, not
colloquial or merely fluent general English. The formula should state the fact
on which the explanation depends. After writing
\(\operatorname{grade} M=n\), say precisely which evaluation map remains to be
proved injective or surjective.

Define every paper-specific term, symbol, statistic, and construction before
using it. Typography does not define a term; emphasizing an unexplained word
with italics can make the interruption worse by suggesting that the reader
should already recognize a formal concept. Introduce nonstandard terminology
only when it names a genuine mathematical object or condition and will be used
consistently. Recall a less familiar standard term when its precise meaning is
load-bearing or when the expected audience may not share one convention for it.

Bad:

> The defect of \(f\) vanishes.

Better:

> Define \(d(f)=\dim\ker f\). Since \(f\) is injective, \(d(f)=0\).

An evaluative adjective does not define a construction. Words such as
`natural`, `canonical`, `ordinary`, `distinguished`, `direct`, and `explicit`
should be supported by a stated property or omitted.

Bad:

> There is a natural map from \(\operatorname{Hom}_R(R,M)\) to \(M\).

Better:

> Evaluation at \(1\) defines the map
> \[
> \operatorname{Hom}_R(R,M)\longrightarrow M,\qquad f\longmapsto f(1).
> \]

Prefer the mathematical property itself to an unexplained label. For example:

- do not say `projective boundary` when the argument means that an
  indecomposable module is projective; say the latter;
- do not call a module `small` or `bounded` before stating the finiteness
  property actually used, such as finite projective dimension, finite length,
  or a uniform bound on the ranks in a resolution;
- before using torsionless or cotorsionless modules, state the concrete
  embedding, quotient, or duality property needed in the argument; and
- do not import internal research labels such as `route`, `stratum`, `wall`,
  `core`, or `profile` unless they name a genuinely useful object that has
  first been defined mathematically.

State module side, field assumptions, and algebra class explicitly wherever the
argument depends on them. Internal project conventions are not something the
reader of the paper knows.

Use one established term for one notion. Do not add a near-synonym merely to
emphasize a property that the notation already makes explicit: a paper that has
fixed the term `Gorenstein-projective` does not also need `maximal
Cohen--Macaulay` for the same class of modules. Conversely, do not introduce an
informal English name for a condition already expressed more clearly by
notation; if the argument uses \(\operatorname{pd}_A M<\infty\), do not call
\(M\) `resolvable` unless that term is defined, used consistently, and
genuinely reduces the reader's work.

Every long-lived symbol adds to the reader's working memory. Introduce a symbol
only when it has a continuing role or materially shortens the argument. Prefer
\(\Omega M\) to a new symbol \(N:=\Omega M\), and
\(\operatorname{Ext}^n_A(M,A)\) to a new symbol for that group, unless the alias
is used often enough to make the proof materially easier to read. Confine dummy
variables for individual morphisms or test objects to the paragraph in which
they are used.

Use a formula when it states a relation more clearly than prose, and use prose
to explain the purpose and logical role of the relation.

### Formal definitions and constructions

Choose between a numbered environment and an inline introduction according to
the later mathematical role of the notion. Use a `Definition` environment for a
named notion which has a continuing role, especially when it is used in several
statements or sections, has several clauses, is introduced by the paper, or
benefits from a numbered reference. Closely related notions should normally be
grouped in one definition so that their relationship is visible.

Bad:

> Call a sequence regular if it satisfies conditions (1)--(3).

followed several pages later by repeated appeals to regularity.

Better:

```tex
\begin{definition}\label{def:regular-sequence}
A sequence is \emph{regular} if it satisfies the following conditions.
\begin{enumerate}
\item ...
\item ...
\item ...
\end{enumerate}
\end{definition}
```

Use a `Construction` environment for an assignment, algorithm, recursion, or
sequence of choices whose input and output will be used later. State the input,
the output, and any dependence on choices. Prove well-definedness immediately
when it is short, or in a separate result when it is substantial.

Keep a definition in prose when it is a standard one-sentence reminder, local
notation, or a term used only in the immediately following argument.

Bad:

```tex
\begin{definition}
For the rest of this proof, put \(K=\ker f\).
\end{definition}
```

Better:

> For the rest of this proof, put \(K=\ker f\).

The introduction may preview a notion in prose, but the body must give its
complete formal definition before any result depends on it. For a definition
imported from the literature, put the exact source locator in the optional
heading, for example

```tex
\begin{definition}[{\cite[Definition~2.3]{AuthorKey}}]
```

and separate the source definition from any new specialization or convention.
Use a combined `Definition--Proposition` only when the definition and its
immediate existence, independence, or basic properties are most naturally read
as one result. Apply these choices consistently across the paper: the formal
status of a notion should reflect its mathematical role, not merely whether it
is new or imported.

## 4. Make the organization mathematical

The abstract should identify the setting, problem, and principal results in
language available to the intended audience. It must be understandable without
the introduction and should not contain unexplained terminology, proof
machinery, drafting history, or defensive commentary. It is not a compressed
table of contents.

Bad:

> We derive a refined enumeration by a new recursive method.

Better:

> We count finite partially ordered sets according to their number of elements
> and derive a recurrence for these numbers.

### Give the introduction its own job

The introduction should give a governing mathematical question and a clear
hierarchy of results. Explain the familiar setting, formulate the problem,
state the principal results precisely, distinguish the new contribution from
known work, and indicate the proof strategy when that helps the reader see why
the announced ingredients enter. The introduction is mathematical front
matter, not a preliminary section: do not interrupt this route with routine
declarations about module side, path-composition order, representative choices,
variance, or standard notation.

This placement rule is specific to the introduction. Standard vocabulary and
conventional notation belonging to the paper's stated audience may be used
there before the closing conventions block. Do not require a definition of a
path algebra before mentioning path algebras, or a declaration of arrow order
before a sentence whose meaning is independent of that order. Likewise, a
Morita-invariant introductory assertion need not be interrupted by the choice
of a basic representative. Forward readability requires the introductory
passage to be meaningful when encountered; it does not require every harmless
global convention to precede its first mention.

An introductory theorem must nevertheless be understandable at the level at
which it is stated. Define every paper-specific term and symbol needed to read
it, and fix a convention locally when different choices change the meaning of
the statement or of a displayed formula. A pointer to a later section is not a
definition. An informal introductory preview also does not relieve the body of
giving the complete formal definition before a proof or later result depends on
it. Once the introduction ends, apply the ordinary first-occurrence standard
strictly.

Close the introduction with two visibly separate, bold, unnumbered blocks in
the following order:

- **Organization.** Explain the logical route through the paper and how the
  sections contribute to the main results. Do not merely paraphrase the table
  of contents.
- **Conventions and notation.** Collect the global assumptions, choices, and
  durable notation needed for the body, including module side,
  path-composition order, base-field conventions, representative choices, and
  variance when relevant. Keep proof, motivation, and substantive mathematical
  development out of this block.

Use the manuscript's existing unnumbered environments when available;
otherwise implement these as bold unnumbered paragraph headings. The blocks
have different reader functions and must not be merged.

A heading should identify the mathematical content below. It should name the
principal object and indicate what the section does with it: formulate a
question, give a construction or calculation, establish a relation or result,
provide examples, or treat a special case. Choose the grammatical form that
states this purpose naturally and precisely.

Bad heading:

> The second construction

Better heading:

> Completion of metric spaces by Cauchy sequences

Bad heading:

> The recursive step

Better heading:

> Classification of nilpotent operators by induction on dimension

Bad heading:

> Modules of projective dimension one

Better headings, depending on the content of the section:

> Classification of modules of projective dimension one

> Examples of modules of projective dimension one

> A homological criterion for projective dimension one

Read the table of contents by itself. The intended reader should be able to
distinguish the sections and predict the mathematical purpose of each one.
Check the hierarchy also for repetitive or artificial syntax: several headings
may be individually intelligible but collectively sound mechanical because the
same grammatical template has been imposed on all of them.

Place the smallest useful example before or alongside a new encoding,
recurrence, or recursive construction when the example is needed to understand
the general definition. Examples should motivate a question, distinguish
notions, demonstrate a construction, test a boundary case, or show the force of
a theorem. Their number alone says nothing about readability.

Keep the conceptual argument visible in the main text. Move extensive case
analysis or calculation to an appendix when it interrupts that argument, but
state its result and role in the main text.

### Keep optional interpretation optional

Related theories, alternative terminology, historical associations, and
possible future uses can enrich a paper, but they should not obstruct the main
argument. Put them after the relevant mathematics has been made clear, often in
a short remark. Define the associated terminology and say concretely what
connection is being observed.

For instance, if a vanishing condition under study is to be related to
Gorenstein-projective modules or to the singularity category, first develop the
argument in the paper's own terms. A later remark may then define that
terminology and explain what additional structure it suggests. A bare sentence
equating several unintroduced names adds no usable information.

## 5. Expose the logic of statements and proofs

Explain in the preceding prose why a theorem, lemma, proposition, corollary, or
example is being given. Do not add a descriptive caption merely to summarize or
advertise it. Use a name only when it is conventional or when the paper
deliberately introduces a genuinely named statement.

Bad:

```tex
\begin{lemma}[One-step vanishing trick]
```

Better:

> The next lemma reduces vanishing in degree \(n\) to vanishing in degree
> \(n-1\).

followed by

```tex
\begin{lemma}
```

The statement should contain the objects, hypotheses, and conclusions needed to
understand it locally. Mirror numbered parts in the proof and label the actual
directions of an equivalence. Treat each direction label as a heading ending in
a colon. State explicitly when a part follows by duality or from an earlier
part. Avoid phrases such as `the nontrivial direction` when the reader must stop
to determine which implication is meant; it is fine for one direction to be
immediate, but say explicitly why it is immediate.

Bad:

> The converse is similar.

Better:

> \((2)\Rightarrow(1)\): Assume that \(gH=Hg\) for every \(g\in G\). Then
> \(gHg^{-1}=H\) for every \(g\), so \(H\) is normal.

This matters particularly for conjecture implications. Say whether an
implication is between the fixed-algebra assertions or between the universal
ones, and where the argument replaces the algebra by another one. Do not let
the manuscript blur the two levels the way an abbreviation can.

Do not compress a load-bearing step merely because an expert could reconstruct
it. Include the intermediate implication or calculation which explains why the
conclusion follows, why a hypothesis is present, why a construction is well
defined, or why collective closure under finite direct sums is stronger than an
objectwise check.

Suppose that

\[
S_n=\sum_{k=0}^{n}2^k.
\]

Bad:

> Rearranging the sum gives \(S_n=2S_{n-1}+1\).

Better:

\[
S_n
 =1+\sum_{k=1}^{n}2^k
 =1+2\sum_{k=0}^{n-1}2^k
 =1+2S_{n-1}.
\]

A long proof should reveal its dependency structure. Use an internal claim when
several later steps depend on it, descriptive headings for a genuine case
division, and short transitions for a linear argument. Display a diagram when
several maps or universal properties would otherwise have to be reconstructed
from prose: a commutative diagram is normally helpful when three or more objects
participate in a factorization, pullback, pushout, exact sequence, comparison of
two resolutions, or comparison of induced Hom or Ext maps. Label the maps and
state the exact kernel, image, or universal property used.

Choose an internal label according to its logical role. A `Step` is one stage of
a sequential argument, a `Case` is one branch of a case division, a `Claim` is
an assertion proved locally and used later, and `Part (1)`, `Part (2)`, and so
on mirror the numbered conclusions of the statement. Announce a proof divided
into several steps before the first step, and number steps, cases, or claims
only when more than one occurs. Length alone does not require numbered claims:
use short transitions when the argument is linear. Set the label and a
descriptive title in bold when a short title is useful, and attach the assertion
or case condition immediately. Do not use an unexplained italic noun phrase as
an internal heading.

Bad:

```tex
\emph{Localized modules.}
```

Better:

```tex
We divide the proof into two steps.

\medskip
\noindent\textbf{Step 1: Injectivity after localization.}
For every prime ideal \(\mathfrak p\), the map \(f_{\mathfrak p}\) is
injective.
```

A step normally continues as part of the surrounding proof; it does not need a
separate `Proof of Step 1` heading or an internal end-of-proof symbol. Retain a
separate proof and end-of-proof symbol for an internal claim when that claim is
most naturally read as a local lemma. An internal claim should state an exact
mathematical assertion, not an editorial description of the proof: write `By
Claim 2, it remains to prove the two vanishing statements in (4.3)` rather than
`we now state what remains to be proved`. Once a reduction claim has been
proved, do not repeat its construction after proving its hypotheses. Do not
fragment a proof into claims which are used only in the next sentence; the
purpose of the structure is to expose the dependency graph, not to add
typography.

Use an exact numbered reference or repeat the assertion when a relative phrase
would require backtracking.

Bad:

> By the previous result, the map is injective.

Better:

> Proposition 4.3 gives \(\ker f=0\); hence \(f\) is injective.

State the precise mathematical content imported from a source, including the
needed hypotheses and conventions, and give an exact locator. Separate that
statement from any new specialization or application. The reader should not
have to know in advance what a named correspondence or classification says, nor
consult the source merely to discover why it is relevant. If only a numerical
consequence or a restricted case is needed, state that consequence rather than
invoking a larger theory rhetorically.

Do not use an author's name, a broad citation, or a coined theorem name in place
of the assertion. Attaching an author's name to an ordinary descriptive phrase
turns it into an apparent theorem name: `Han's vanishing criterion` suggests an
established name which the reader should already know. Introduce the result
instead:

```text
To decide when the Hochschild homology of A vanishes in all large degrees, we
use the following criterion proved by Han [citation].
```

Then state the criterion. Similarly, prefer `Auslander and Reiten prove that
...` to `the vanishing theorem of Auslander--Reiten` unless the latter is a
genuinely established theorem name. The expressions `the following criterion`,
`the following numerical equality`, and `the following bijection` are ordinary
descriptions of results being introduced at that point; they do not claim a
standard name. This distinction remains important when the precise statement
immediately follows, because a homemade possessive label still makes the reader
stop to decide whether it denotes familiar terminology.

## 6. Report computational evidence honestly

When the paper rests on a finite computation, state its exact scope, the
conventions under which it was run, and what it does and does not establish. A
computed range is not a theorem about all algebras. If the paper presents a
counterexample found by search, give the object explicitly enough that the
reader can verify it independently, and cite the certificate.

## 7. Review the paper as a reader

Reread the manuscript in order without using later explanations to repair an
earlier passage. For a substantial review, follow the
[continuous first-reader protocol](../../read-research-paper/references/first-reader-review.md);
the reader should receive no research notes, conversation history, later
portion of the manuscript, or writer-side diagnostic reports. Calling a
reviewer blind does not certify the paper, and a list of reported defects is
not a sufficient checklist: repeated local defects may reveal that the
exposition needs a broader rewrite.

Continuous and skeptical editorial readings answer different questions. A
continuous reader tests whether the paper can be followed at first encounter.
A skeptical editor reads the complete paper and runs two audits: what
reader-visible loss would result from deleting each transition, remark,
qualification, repeated explanation, informal label, or apparent theorem name;
and whether every retained substantive statement or result pointer has an
exact subject, predicate, status, and referent rather than a meaning
recoverable only by guesswork. Follow
[skeptical-editor protocol](../../read-research-paper/references/skeptical-editor-review.md)
for that pass. A
passage is not justified merely because its purpose can be reconstructed or
because it states a true limitation, and an understandable result pointer is
not justified when it sounds like an established theorem name or hides the
exact assertion being used.

Before declaring a revision complete, check:

1. Can the abstract be understood without the introduction?
2. Does the introduction state a governing question and a hierarchy of new
   results?
3. Does the introduction close with separate bold unnumbered **Organization**
   and **Conventions and notation** blocks, with routine global setup deferred
   there unless an earlier passage is convention-sensitive?
4. Does the table of contents give a useful mathematical synopsis?
5. Does every sentence have a clear subject, predicate, referent, and purpose?
6. Is every term and symbol meaningful at its first occurrence?
7. Are module side, field assumptions, and algebra class stated wherever the
   argument depends on them?
8. Do `Definition`, `Construction`, and inline introductions consistently
   reflect the later mathematical roles of the notions being introduced?
9. Does every named object need its own symbol, and has every load-bearing
   configuration of several maps been considered for a commutative diagram?
10. Does every substantial proof expose its directions, dependencies, and
   load-bearing steps, with the fixed-algebra or universal level of each
   implication explicit?
11. Is each imported result stated precisely, separated from the paper's new
   contribution, and free of coined theorem names?
12. Does every computational claim state its exact scope?
13. Are optional interpretations placed after, rather than in place of, the
   main explanation?
14. Has every reference to prompts, instructions, review history, internal
   records, agent behavior, or the revision process been removed?
15. Have recurring causes been repaired throughout the manuscript rather than
   only at the locations first reported?
16. Would deleting each remark, qualification, transition, informal alias, or
   result name cause an identifiable loss to the intended reader?
17. Does every retained result pointer, citation-based application, informal
   alias, and apparent result name identify an exact mathematical referent and
   evidence status without requiring guesswork?
18. At every major section or subsection boundary, do the heading and opening
   passage provide an adequate local handoff from the work just completed,
   without relying only on a distant Organization block or adding generic
   roadmap boilerplate?

Compilation checks the artifact, not the reader's understanding. For an ordinary
prose or proof-structure revision, compile the paper and inspect the log, but do
not routinely render PDF pages. Inspect rendered pages only when there is a
genuine visual question, such as a complicated figure, diagram, or table,
suspected clipping or collision, an unusual page break, or another concrete
layout problem. When such a check is justified, inspect only the affected pages.
