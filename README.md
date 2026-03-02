# Codex Package (Codex-Only Branch)

This repository branch contains only the assets prepared for Codex use.

## Included

- `.agents/skills/` — 56 Codex-usable skills (each with `agents/openai.yaml` metadata)
- `.codex/` — Codex resource packs:
  - `agents/`
  - `commands/`
  - `contexts/`
  - `examples/`
  - `rules/`
  - `scripts/`
  - `tests/`
  - `AGENTS.md`
  - `config.toml`
  - `TRANSFER_REPORT.md`
- Root docs:
  - `AGENTS.md`
  - `README-CODEX-TRANSFER.md`

## Quick Start

1. Clone the repo.
2. Checkout branch `codex/codex-only`.
3. Run Codex from this repository root.
4. Use skills from `.agents/skills/`.
5. Use playbooks from `.codex/commands/`, `.codex/agents/`, and `.codex/contexts/`.

## Notes

- This branch intentionally excludes Claude/Cursor/OpenCode runtime assets.
- Some skills originally designed around hook automation are preserved as guidance-first workflows in Codex.
- See `.codex/TRANSFER_REPORT.md` for transfer details.
