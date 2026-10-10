# Nexus Learning: Master Knowledge Base & Agent Guidelines (`AGENTS.md`)

This document serves as the master reference, binding architectural blueprint, and mandatory instruction set for any AI assistant (Antigravity, Gemini, Cursor, Copilot) and developer working on `nexus-learning`.

---

## 1. Universal AI Git & Commit Policy (STRICT - MUST FOLLOW)

### A. Never Commit (`git commit` is FORBIDDEN for AI)
- The AI assistant **MUST NEVER** execute `git commit`.
- All Python pipelines, training scripts, dataset generators, and newly created files must remain **locally uncommitted** in the git working tree.
- The user will personally inspect the diffs, verify all changes in GitHub Desktop / Git CLI, and execute `git commit` manually.

### B. Never Push (`git push` is FORBIDDEN for AI)
- The AI assistant **MUST NEVER** execute `git push` to `origin` or any remote repository.
- Never publish branches or code online to GitHub. All modifications must stay strictly in the local workspace.

### C. Git Branching & Naming Standards
- **Feature Branch Prefix**: MUST use the full prefix **`feature/`** (lowercase), followed by kebab-case (e.g., `feature/pgvector-indexing`, `feature/trajectory-curator`).
  - **STRICTLY PROHIBITED**: Never use shorthand prefixes like `feat/`. Always use `feature/`.
- **Bugfix Branch Prefix**: Use `fix/<issue-name>` or `feature/<issue-name>`.
- **Base Branch**: Every feature or fix branch MUST branch directly off **`dev`** (never from `main`).
- **Workflow**: Branch off `dev` -> Perform work -> Leave changes uncommitted for user review -> User manually commits -> User pushes to `origin/feature/<branch-name>` -> PR targets `dev`.

### D. Mandatory Self-Updating Documentation Policy (Zero-Forgotten Rule)
- Whenever ML pipelines, embeddings, or vector indexing strategies are updated, immediately update `AGENTS.md` and `GEMINI.md`.

### E. Mandatory Prohibition on Automated Browser Testing (STRICT ZERO BROWSER TEST RULE)
- **Automated Browser Testing Strictly Forbidden**: The AI assistant **MUST NEVER** launch automated browser subagents or headless test sessions.
- **Code-Level Verification Only**: All verification must be performed strictly at the **code level** (`pytest`, `ruff check`, pipeline validation).

---

## 2. Directory Structure

```text
nexus-learning/
├── src/
│   ├── curation/               # Execution trace & trajectory curation
│   ├── embeddings/             # Vector embedding generators (pgvector)
│   ├── extraction/             # Post-execution skill extractor
│   └── evaluation/             # Offline golden evaluation pipelines
├── datasets/                   # Curated benchmark datasets (gitignored large files)
├── tests/
├── pyproject.toml
└── README.md
```

---

## 3. Principles Transferred from eShop & SRV

1. **Database Isolation & pgvector Security (SRV Mandate)**:
   - Connects to PostgreSQL 16 with `pgvector` strictly via loopback (`127.0.0.1:5432`) or internal Docker network. Zero public IP binding.
2. **Mandatory Tenant Scoping (`tenant_id`)**:
   - Learned skills and embedding spaces must be scoped by `tenant_id` to prevent cross-tenant knowledge leaks.
3. **Zero Plaintext Secrets**:
   - Training keys, model registry tokens, and database credentials must never be committed.

---

*Authorized by Dapplesoft Architecture & Nexus Governance Council*
