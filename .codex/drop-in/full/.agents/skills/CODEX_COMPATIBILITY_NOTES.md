# Codex Compatibility Notes

All skills from `skills/` were ported to `.agents/skills/` with Codex metadata (`agents/openai.yaml`).

## Partial-support caveat
Codex does not provide Claude-style hook automation (`PreToolUse`, `PostToolUse`, etc.).

Skills that mention hook setup still work as guidance and manual workflows, but their automatic hook-trigger behavior is partial in Codex.

Common affected areas:
- continuous learning / observation hooks
- compact suggestion hooks
- config/security scanning for legacy `.claude` layouts
