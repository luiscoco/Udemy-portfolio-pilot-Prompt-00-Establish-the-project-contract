# PortfolioPilot — Project State

Single source of truth for progress. Update at the end of every milestone with **actual** results.

- **Last updated:** 2026-09-30
- **Last completed milestone:** 00 — Project contract and plan
- **Next milestone:** 01 — Verify versions and prerequisites
- **Deployment status:** not deployed; no cloud resources exist.

## Milestone status

| # | Milestone | Status | Notes |
| --- | --- | --- | --- |
| 00 | Project contract and plan | Done | Documentation only |
| 01 | Verify versions and prerequisites | Not started | |
| 02 | Scaffold the monorepo and shared contracts | Not started | |
| 03 | Build the accessible frontend shell | Not started | |
| 04 | Add the first Claude SDK vertical slice | Not started | |
| 05 | Start PostgreSQL and Redis locally | Not started | |
| 06 | Create the Prisma schema and deterministic seed | Not started | |
| 07 | Implement authentication and authorization | Not started | |
| 08 | Build portfolio and transaction APIs | Not started | |
| 09 | Implement valuation and performance calculations | Not started | |
| 10 | Connect the portfolio UI and watchlist | Not started | |
| 11 | Build deterministic provider adapters | Not started | |
| 12 | Add live providers and resilient ingestion | Not started | |
| 13 | Implement caching and the transactional outbox | Not started | |
| 14 | Build replayable authenticated SSE on the API | Not started | |
| 15 | Add frontend streaming and snapshot recovery | Not started | |
| 16 | Build the complete live news experience | Not started | |
| 17 | Create authorized custom tools | Not started | |
| 18 | Build grounded portfolio chat | Not started | |
| 19 | Stream agent answers without duplicate text | Not started | |
| 20 | Implement resumable conversations and structured analysis | Not started | |
| 21 | Build portfolio impact and research recommendations | Not started | |
| 22 | Add recommendation cards and configurable alerts | Not started | |
| 23 | Add focused subagents and an MCP integration | Not started | |
| 24 | Add reusable skills and policy hooks | Not started | |
| 25 | Implement approvals and explicit cancellation | Not started | |
| 26 | Manage context and enforce usage budgets | Not started | |
| 27 | Move execution into a durable worker | Not started | |
| 28 | Persist SDK sessions across restarts | Not started | |
| 29 | Harden the application and execution boundary | Not started | |
| 30 | Add distributed recovery and operational controls | Not started | |
| 31 | Build a meaningful automated test suite | Not started | |
| 32 | Add AI evaluation and observability | Not started | |
| 33 | Build production containers and release CI | Not started | |
| 34 | Generate and validate Azure infrastructure | Not started | |
| 35 | Create Kubernetes deployment and release procedures | Not started | |
| 36 | Finish the capstone and teaching materials | Not started | |

## Environment observed (2026-09-30)

| Tool | Observed | Notes |
| --- | --- | --- |
| OS | Windows 11 Home (10.0.26200) | PowerShell and Git Bash available |
| Node.js | v24.21.0 | LTS suitability to be confirmed in milestone 01 |
| npm | 11.19.0 | |
| git | 2.52.0.windows.1 | Repository on `main`, remote `origin` on GitHub |
| Docker | Not checked | Checked in milestone 01 |

## Latest milestone report — 00

**What works:** The project contract, assistant pointer file, 36-milestone plan, state tracker, and
ADR index exist. No application code has been generated.

**Changed files (all new):**
- `AGENTS.md`, `CLAUDE.md`
- `docs/project-plan.md`, `docs/project-state.md`
- `docs/decisions/README.md`, `docs/decisions/0001-architecture-baseline.md`
- `docs/lessons/00-project-contract.md`
- `README.md` (added after the milestone at the user's request; a student-facing explanation of
  Prompt 00. Milestone 36 replaces it with the full application README.)

**Check results:** Documentation-only milestone; no build, lint, or test tooling exists yet.
Verified that the workspace was empty beforehand, so no existing instruction files were overwritten.

**How to demonstrate:** Open `AGENTS.md`, then `docs/project-plan.md`. Start a fresh assistant
session and confirm it reads `CLAUDE.md` → `AGENTS.md` → `docs/project-state.md`.

**Remaining limitations:**
- ~~The folder is not a git repository.~~ Resolved: the user initialized the repository and added
  the GitHub remote; the Milestone 00 docs and README were committed and pushed to `main` on request.
- No versions are pinned yet; that is milestone 01.

## Open decisions and blockers

- Authentication library, live quote/news provider, and gateway controller are decided in their
  milestones (07, 12, 35) and recorded as ADRs.
