---
name: write-research-paper
description: Draft or revise a mathematics manuscript and supervise its exposition reviews. Use for authorized paper edits or review-supervision relays, not proof audits or isolated reader runs.
---

# Write a research paper

Act as mathematics manuscript writer, reviser, or review supervisor according to
the requested turn. Infer scope from the conversation; skill activation never
grants manuscript-edit or publication authority. Preserve settled owner choices
and unrelated work.

In a multi-model workflow, paper production typically proceeds in three phases:
1. **Structure and exposition relay** (`write-research-paper` +
   `read-research-paper`): a writer model drafts or revises from review reports,
   and a reviewer-coordinator model supervises isolated `FR`/`SE` reader
   subagents until mathematical organization, definitions, citations, and
   completeness converge.
2. **Natural math-English and proof-presentation rewrite**
   ([`polish-math-prose`](../polish-math-prose/SKILL.md)): a prose-specialist
   model rewrites AI-like syntax and compressed proof steps with fresh eyes and
   logs substantive mathematical touches in `REVISION-NOTES.md`.
3. **Mathematical diff audit loop**: a logic-specialist model audits the
   `git diff` and `REVISION-NOTES.md` against the pre-polish baseline, and the
   polisher repairs any flagged mathematical regressions until clean.

Before editing, read completely the shared
[exposition standard](references/exposition-standard.md), the
[workflow](references/workflow.md), the
[paper-writing guide](references/paper-writing.md), and the host's relevant
paper overlay. Reread them before the next edit after context compaction or a
session restart. The guide's private-process rules apply to every repair:
never answer an owner or reviewer question, or report a finding, inside the
manuscript. Locate the manuscript revision and existing writing state. For a
substantial task, adapt [writing-state.md](assets/writing-state.md) without
creating a competing record.

The workflow supports both **decoupled relay turns** (drafting/revising from an
existing report without automatically spawning subagents, or supervising an
isolated review round without editing) and **full-cycle turns** when requested
by the owner. Do not automatically spawn `FR`, `SE`, or `Delta` subagents after
every edit unless the owner's prompt asks to run a review round or full cycle.

When supervising a review round, read only its mode-specific protocol and use
its assets:

| Review | Protocol | Direction and launcher |
|---|---|---|
| Continuous first reading | [continuous](../read-research-paper/references/first-reader-review.md) | [direction](assets/first-reader-direction.md), [launcher](assets/first-reader-launcher.md) |
| Whole-paper editorial audit | [editorial](../read-research-paper/references/skeptical-editor-review.md) | [direction](assets/skeptical-editor-direction.md), [launcher](assets/skeptical-editor-launcher.md) |
| Bounded repair regression | [delta](../read-research-paper/references/delta-review.md) | packet specified in that protocol |

Use fresh isolated readers running `read-research-paper`, never the writer's
context. Withhold drafting history, owner discussion, prior reviews,
diagnostics, expected findings, and proposed repairs. Continuous reading
requires a staged relay; editorial review accepts one frozen packet.

When revising from completed reports, read them completely before editing and
use [revision-batch.md](assets/revision-batch.md) for complete finding
coverage. Compile, complete host gates, and inspect the aggregate diff before
finishing the turn. Do not manufacture an edit when none is needed or prepare a
submission or external publication without separate authority.
