# Mathematics paper skills

Three paired, portable agent skills for owner-directed mathematics-paper writing,
independent exposition review, and natural mathematical prose polishing:

- `write-research-paper` drafts and revises a live LaTeX manuscript, supervises
  independent exposition review, adjudicates findings, and carries accepted
  edits through host-project validation.
- `read-research-paper` performs an isolated continuous first reading,
  skeptical editorial review, or bounded delta regression of a frozen
  manuscript without editing it.
- `polish-math-prose` rewrites AI-like syntax, causative verb compression,
  telegraphic imperative chains, and compressed proof presentations into natural
  `amsart` mathematical English with fresh eyes (logging substantive mathematical
  argument touches in `REVISION-NOTES.md`), and repairs any defects flagged in a
  subsequent mathematical diff audit.
- `coordinate-research-paper` routes the three phases below between the
  writer, isolated readers, polisher, and math auditor on the owner's behalf,
  keeps a cross-round finding ledger, and stops at owner gates. It runs in a
  top-level session that can spawn subagents (for example Claude Code).

## Multi-model workflow

1. **Phase 1 — Structure & exposition relay (`write-research-paper` +
   `read-research-paper`):** A writer model (e.g. Codex or Claude) drafts or
   revises from review reports, and a reviewer-coordinator model (e.g. Claude
   Opus) supervises isolated `FR`/`SE` reader subagents until mathematical
   architecture, definitions, symbol choices, citations, and missing steps
   converge.
2. **Phase 2 — Natural math-English & proof-presentation rewrite
   (`polish-math-prose`, `rewrite` mode):** A prose-specialist model (e.g.
   Gemini 4 Argon) reads the `.tex` files with fresh eyes (ignoring prior
   `.research-scratch` review logs and `REVISION-BATCH.md`), rewrites cumulative
   patch syntax and compressed proof steps into natural mathematical English,
   and records every substantive mathematical argument touch in
   `REVISION-NOTES.md`.
3. **Phase 3 — Mathematical diff audit loop (mathematical auditor <->
   `polish-math-prose`, `repair` mode):** A logic-specialist model (e.g. Codex)
   audits `git diff` and `REVISION-NOTES.md` against the pre-polish baseline for
   subtle mathematical regressions, quantifier shifts, or dropped hypotheses,
   and the polisher repairs any flagged items until the audit is clean.

The writer owns the shared mathematical-paper exposition standard
(`write-research-paper/references/exposition-standard.md`). The reader and
polisher load that standard through a sibling-relative link. Install the three
skills together and keep their directory layout unchanged. The coordinator is
needed only on the host that runs the relay, but it depends on the other three
skills through relative links, so install all four together there; link it the
same way, for example to `$HOME/.claude/skills/coordinate-research-paper`.

## Install once for supported agents

Clone this repository once at a stable path. Then link all three skill
directories into each agent's user skill directory. Codex and other hosts using
the common agent-skills location read `~/.agents/skills`:

```sh
mkdir -p "$HOME/.agents/skills"
ln -sfn /absolute/path/to/math-paper-skills/skills/write-research-paper \
  "$HOME/.agents/skills/write-research-paper"
ln -sfn /absolute/path/to/math-paper-skills/skills/read-research-paper \
  "$HOME/.agents/skills/read-research-paper"
ln -sfn /absolute/path/to/math-paper-skills/skills/polish-math-prose \
  "$HOME/.agents/skills/polish-math-prose"
```

Claude Code reads `~/.claude/skills`:

```sh
mkdir -p "$HOME/.claude/skills"
ln -sfn /absolute/path/to/math-paper-skills/skills/write-research-paper \
  "$HOME/.claude/skills/write-research-paper"
ln -sfn /absolute/path/to/math-paper-skills/skills/read-research-paper \
  "$HOME/.claude/skills/read-research-paper"
ln -sfn /absolute/path/to/math-paper-skills/skills/polish-math-prose \
  "$HOME/.claude/skills/polish-math-prose"
```

Gemini / Antigravity CLI reads `~/.gemini/config/skills`:

```sh
mkdir -p "$HOME/.gemini/config/skills"
ln -sfn /absolute/path/to/math-paper-skills/skills/write-research-paper \
  "$HOME/.gemini/config/skills/write-research-paper"
ln -sfn /absolute/path/to/math-paper-skills/skills/read-research-paper \
  "$HOME/.gemini/config/skills/read-research-paper"
ln -sfn /absolute/path/to/math-paper-skills/skills/polish-math-prose \
  "$HOME/.gemini/config/skills/polish-math-prose"
```

All hosts follow symlinked skill directories. A single checkout therefore
remains the source used by every workspace and agent. Keep the three packages
together because `read-research-paper` and `polish-math-prose` reference sibling
files by relative links.

Invocation syntax is host-specific. In Codex, use `$write-research-paper`,
`$read-research-paper`, or `$polish-math-prose`; in Claude Code or Antigravity,
use `/write-research-paper`, `/read-research-paper`, or `/polish-math-prose`.
A host may also select them from their descriptions.

## Update

Pull this repository at its canonical checkout. All user-level symlinks then
resolve to the updated files. Tag a known-good revision before manuscript work
that needs a reproducible skill version.

## Host-project boundary

These skills contain the portable exposition, workflow, review, anti-pattern,
and template resources. A host project may add local authorship rules,
manuscript state, compilation gates, vocabulary diagnostics, and publication
conventions through its own instructions or paper-writing overlay.

## Layout

```text
skills/
├── coordinate-research-paper/
│   ├── SKILL.md
│   ├── agents/
│   ├── assets/
│   └── references/
├── polish-math-prose/
│   ├── SKILL.md
│   ├── agents/
│   └── references/
├── read-research-paper/
│   ├── SKILL.md
│   ├── agents/
│   └── references/
└── write-research-paper/
    ├── SKILL.md
    ├── agents/
    ├── assets/
    └── references/
```

## License

MIT. See [LICENSE](LICENSE).
