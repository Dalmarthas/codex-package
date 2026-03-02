# Skill Conflict Audit (Codex Branch)

This audit reviews overlap/contradiction risk after combining skill sources.

## High-Risk Collisions Found

1. `continuous-learning` vs `continuous-learning-v2`
- Conflict type: version overlap / competing workflows for the same problem.
- Evidence: both define automatic session learning pipelines; v2 explicitly supersedes v1 model.
- Resolution: keep both files, but set `allow_implicit_invocation: false` for both to avoid accidental auto-selection.

2. Hook-dependent workflow skills vs Codex runtime expectations
- Skills: `continuous-learning`, `continuous-learning-v2`, `strategic-compact`, parts of `security-scan`.
- Conflict type: runtime assumption mismatch (hook automation in docs vs Codex behavior).
- Resolution: mark these as explicit-use skills by disabling implicit invocation where appropriate; keep as guidance/manual workflows.

3. Installer/meta skills in development sessions
- Skills: `configure-ecc`, `skill-stocktake`, `security-scan`.
- Conflict type: operational/meta tasks can distract from implementation tasks if auto-triggered.
- Resolution: disable implicit invocation.

4. Non-development domain skills inside engineering bundle
- Skills: `article-writing`, `content-engine`, `investor-materials`, `investor-outreach`, `market-research`, `visa-doc-translate`.
- Conflict type: intent overlap noise during coding tasks.
- Resolution: disable implicit invocation and exclude from the `universal-dev` drop-in pack.

## Overlap Groups (Non-Conflicting, Intentional)

- Testing stack: `tdd-workflow`, language-specific testing skills, `e2e-testing`, `eval-harness`, `verification-loop`.
- Security stack: `security-review` + framework-specific security skills.
- Architecture stack: `backend-patterns`, `api-design`, `database-migrations`, `deployment-patterns`, `docker-patterns`.

These are layered rather than contradictory.

## Policy Changes Applied

Set `allow_implicit_invocation: false` for:
- `configure-ecc`
- `continuous-learning`
- `continuous-learning-v2`
- `strategic-compact`
- `security-scan`
- `skill-stocktake`
- `article-writing`
- `content-engine`
- `investor-materials`
- `investor-outreach`
- `market-research`
- `visa-doc-translate`

## Drop-In Packs Prepared

- `.codex/drop-in/universal-dev/` (conflict-safe default)
- `.codex/drop-in/full/` (all skills)

Each pack includes:
- `.agents/skills/`
- `.codex/` playbooks
- `AGENTS.md`
- `LICENSE`
- manifest + README
