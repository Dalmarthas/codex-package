# Codex Transfer Summary

This repository was audited and ported for Codex usability, with content moved into Codex-oriented structure and compatibility notes added.

## What Was Done

1. Ported all skills from `skills/` into `.agents/skills/`.
2. Ensured each skill in `.agents/skills/` has Codex metadata at `agents/openai.yaml`.
3. Added Codex resource packs under `.codex/`:
   - `.codex/agents/`
   - `.codex/commands/`
   - `.codex/contexts/`
   - `.codex/examples/`
   - `.codex/rules/`
   - `.codex/scripts/`
   - `.codex/tests/`
4. Renamed example guidance from `*CLAUDE.md` naming to `*AGENTS.md` naming in `.codex/examples/`.
5. Normalized many legacy path references from `.claude` to Codex-oriented locations (`.codex` / `.agents`).
6. Added transfer documentation:
   - `.codex/TRANSFER_REPORT.md`
   - `.agents/skills/CODEX_COMPATIBILITY_NOTES.md`

## Applicability Decisions

Transferred:
- Codex-applicable skills, agents, commands, contexts, examples, non-hook rules, validator/codemap scripts, and relevant tests.

Skipped or marked partial-support:
- Hook-dependent automation and Claude runtime components that do not map directly to Codex hook behavior.
- Claude-specific session/package-manager/claw flows that assume `.claude` runtime semantics.

## Current State

- Skills in `skills/`: 56
- Skills in `.agents/skills/`: 56
- `openai.yaml` metadata files in `.agents/skills/*/agents/`: 56

## Notes

- Codex does not currently support Claude-style hook automation in the same way. Skills that rely on hooks are still useful as manual workflows, but automatic hook triggers are partial in Codex.
- See `.codex/TRANSFER_REPORT.md` for explicit per-folder transfer/skip rationale.
