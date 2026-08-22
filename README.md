# Mathematics paper skills

Two paired Codex skills for owner-directed mathematics-paper writing and
independent exposition review:

- `write-research-paper` drafts and revises a live LaTeX manuscript, supervises
  independent review, adjudicates findings, and carries accepted edits through
  regression and host-project validation.
- `read-research-paper` performs an isolated continuous first reading,
  skeptical editorial review, or bounded delta regression of a frozen
  manuscript without editing it.

The writer owns the shared mathematical-paper exposition standard. The reader
loads that standard through a sibling-relative link while remaining isolated
from the writer workflow and project state. Install the two skills together and
keep their directory layout unchanged.

## Install for every Codex workspace

Clone this repository once at a stable path. Then link both skill directories
into the user skill directory:

```sh
mkdir -p "$HOME/.agents/skills"
ln -sfn /absolute/path/to/math-paper-skills/skills/write-research-paper \
  "$HOME/.agents/skills/write-research-paper"
ln -sfn /absolute/path/to/math-paper-skills/skills/read-research-paper \
  "$HOME/.agents/skills/read-research-paper"
```

Codex follows symlinked skill directories. A single checkout therefore remains
the source used by every workspace. Restart Codex if an updated skill does not
appear immediately.

Invoke the skills explicitly as `$write-research-paper` and
`$read-research-paper`, or let Codex select them from their descriptions.

## Update

Pull this repository at its canonical checkout. All user-level symlinks then
resolve to the updated files. Tag a known-good revision before manuscript work
that needs a reproducible skill version.

## Host-project boundary

These skills contain the portable exposition, workflow, review, and template
resources. A host project may add local authorship rules, manuscript state,
compilation gates, vocabulary diagnostics, and publication conventions through
its own instructions or paper-writing overlay. Such project-specific material,
research records, manuscripts, and private evaluation gold do not belong in
this repository.

## Layout

```text
skills/
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
