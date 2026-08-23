# Mathematics paper skills

Two paired, portable agent skills for owner-directed mathematics-paper writing
and independent exposition review:

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

## Install once for supported agents

Clone this repository once at a stable path. Then link both skill directories
into each agent's user skill directory. Codex and other hosts using the common
agent-skills location read `~/.agents/skills`:

```sh
mkdir -p "$HOME/.agents/skills"
ln -sfn /absolute/path/to/math-paper-skills/skills/write-research-paper \
  "$HOME/.agents/skills/write-research-paper"
ln -sfn /absolute/path/to/math-paper-skills/skills/read-research-paper \
  "$HOME/.agents/skills/read-research-paper"
```

Claude Code reads `~/.claude/skills`:

```sh
mkdir -p "$HOME/.claude/skills"
ln -sfn /absolute/path/to/math-paper-skills/skills/write-research-paper \
  "$HOME/.claude/skills/write-research-paper"
ln -sfn /absolute/path/to/math-paper-skills/skills/read-research-paper \
  "$HOME/.claude/skills/read-research-paper"
```

Both hosts follow symlinked skill directories. A single checkout therefore
remains the source used by every workspace and agent. For another host that
supports `SKILL.md` packages but uses a different discovery directory, create
the same two directory symlinks there; do not copy or fork the skill bodies.
Keep the two packages together because the reader loads the writer's portable
paper-writing guide by a sibling-relative link.

Invocation syntax is host-specific. In Codex, use `$write-research-paper` or
`$read-research-paper`; in Claude Code, use `/write-research-paper` or
`/read-research-paper`. A host may also select them from their descriptions.
Start a new session or use the host's skill-refresh mechanism if an update does
not appear immediately.

## Update

Pull this repository at its canonical checkout. All user-level symlinks then
resolve to the updated files. Tag a known-good revision before manuscript work
that needs a reproducible skill version.

## Host-project boundary

These skills contain the portable exposition, workflow, review, and template
resources. A host project may add local authorship rules, manuscript state,
compilation gates, vocabulary diagnostics, and publication conventions through
its own instructions or paper-writing overlay.

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
