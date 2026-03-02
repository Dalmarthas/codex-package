# Fetch, Install, and Bootstrap Prompt

Use this file to quickly install the Codex package into any project and force consistent skill usage from the first prompt.

## One-Line Install (Codex-Only Package)

Run from your target project root:

```bash
curl -fsSL "https://raw.githubusercontent.com/Dalmarthas/codex-package/refs/heads/codex/codex-only/.codex/scripts/install-codex-package.sh" | bash -s -- .
```

## One-Line Install (Non-Coding Package)

```bash
curl -fsSL "https://raw.githubusercontent.com/Dalmarthas/codex-package/refs/heads/codex/codex-only/.codex/scripts/install-codex-package.sh" | BRANCH="codex/codex-noncoderagents" bash -s -- .
```

## Source Branch Links

- Codex-only: <https://github.com/Dalmarthas/codex-package/tree/codex/codex-only>
- Non-coding: <https://github.com/Dalmarthas/codex-package/tree/codex/codex-noncoderagents>

## Bootstrap Prompt for Codex

Copy/paste this at the start of a new session:

```text
Fetch and install my Codex package first, then use it as default workflow.

Install command:
curl -fsSL "https://raw.githubusercontent.com/Dalmarthas/codex-package/refs/heads/codex/codex-only/.codex/scripts/install-codex-package.sh" | bash -s -- .

Source package:
https://github.com/Dalmarthas/codex-package/tree/codex/codex-only

After install:
1) Read and follow ./AGENTS.md, ./.codex/AGENTS.md, and ./.codex/SKILL_PRECEDENCE.md.
2) Use skills from ./.agents/skills and playbooks from ./.codex by default.
3) When multiple skills apply, follow precedence in ./.codex/SKILL_PRECEDENCE.md.
4) Keep one driving workflow skill at a time; others are supporting.
5) Confirm what was installed and which skills/workflows are active for this task.
```
