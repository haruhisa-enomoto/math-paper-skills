# Launcher notes: skeptical-editor review

<!-- TEMPLATE. Use with the write and read research-paper skills. Editors must not open this. -->

**Editors must not open this file.**

## Setup

- [ ] The complete reading-order manuscript is frozen and its revision is
      recorded in `DIRECTION.md` together with a reproducible content hash.
- [ ] `DIRECTION.md` states audience, promise, length/detail boundary,
      protected content, withheld material, and report destination without
      suspected defects, target phrases, or preferred conclusions.
- [ ] The editor can write its report but cannot edit the manuscript.
- [ ] A fresh subagent with no inherited conversation or research context is
      available.

## Editor identity

    Editor label:
    Subagent identity:
    Launch time:
    Frozen manuscript path:
    Frozen manuscript identity:

## Initialize

Send this message, and nothing else, to a fresh subagent:

    You are the fresh editor in an independent skeptical-editor review. This
    is exposition-review work, not mathematical research; do not load project
    research state. Your editor label is <LABEL>. Use $read-research-paper in
    editorial mode. Read <path>/DIRECTION.md and every guide the skill and
    direction require completely. Do not open or receive manuscript text yet.
    Validate isolation, then reply only: Ready for the frozen manuscript.

If the editor sees the manuscript before confirming readiness, mark the run
invalid and begin again with a new editor.

## Supply the manuscript

After readiness confirmation, send only:

    Frozen manuscript: <PATH>. Verify its recorded identity, complete the
    two-pass necessity-and-referential-precision skeptical-editor review, and
    write the report required by DIRECTION.md.

Do not react to findings or provide further substantive instructions while the
run is active.

## Completion

Check process only: exact revision, complete manuscript coverage, both audit
verdicts, required inventories, isolation statement, and report creation. The
writer later adjudicates the content.

    Status: complete | invalid | aborted
    Report:
    Failure and point of discovery, if any:
