# Nexus Learning: Gemini & AI Model Guidelines (`GEMINI.md`)

This document is aligned 1:1 with `AGENTS.md`.

## Mandatory Rules Summary
1. **Never Commit / Never Push:** Forbidden for AI. All changes remain locally uncommitted for human review.
2. **Branching:** Branch off `dev` using `feature/<name>`. Never use `feat/`.
3. **Zero Browser Testing:** Code-level validation only (`pytest`, `ruff`).
4. **Tenant Isolation:** Enforce `tenant_id` on embeddings and curated skills.
5. **Always Update Documentation:** Synchronize `AGENTS.md` and `GEMINI.md` immediately upon code changes.
