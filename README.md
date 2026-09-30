# PortfolioPilot

PortfolioPilot is a stock portfolio manager with a live news feed, portfolio-aware AI chat, cited
news analysis, research recommendations, watchlists, and alerts. The AI runs on the **Claude Agent
SDK**. You will build the application step by step during this course, one prompt at a time, with
a coding assistant in VS Code.

> **Current status:** Prompt 00 is complete. The repository contains the project contract and plan
> only. **There is no application code yet**, so there is nothing to install or run. Milestone 36
> will turn this README into the full application guide.

---

## Prompt 00 — Establish the project contract

### Why this prompt exists

A coding assistant only remembers the current conversation. When you open a new chat, switch
between Claude and GPT, or come back the next day, it has forgotten your architecture, your rules,
and how far you got. Without shared written rules, you risk:

- a second frontend appearing inside Next.js when React is meant to be the only one,
- invented package versions or SDK methods,
- secrets in the browser bundle,
- tests that "pass" without checking anything,
- milestones marked done that were never verified.

Prompt 00 fixes this before any code exists. It writes the rules, the architecture, and the plan
**into the repository**, where every assistant and every future session can read them.

**Rule of thumb:** the repository is the memory, not the chat.

### What the prompt asks the assistant to do

1. Record the **product** and the **required architecture**: React/Vite frontend, Next.js API
   routes only, a background worker, shared packages, PostgreSQL, Redis, and Azure AKS.
2. Record **11 implementation rules**: verify APIs before using them, decimal money arithmetic,
   no secrets in the browser, ownership enforcement, a least-privilege agent, stable events,
   explicit cancellation, honest verification, and no deployment without authorization.
3. Create the contract files and a **36-milestone plan**.
4. **Not** write any application code yet.

### Steps the assistant followed

These are the steps actually taken when the prompt was run:

| # | Step | Why it matters |
| --- | --- | --- |
| 1 | Checked the workspace. It was empty. | The contract says never to overwrite existing instructions, so the assistant checks first. |
| 2 | Checked the parent folder for instruction files and found the course prompt pack (`.docx`). | Context outside the repo can affect the plan. |
| 3 | Read the prompt pack's list of Prompts 01–36. | The plan's milestone numbers and titles now match the prompts you will paste later. |
| 4 | Recorded the local tools: Node v24.21.0, npm 11.19.0, git 2.52 (Windows 11). | This gives a baseline. Milestone 01 checks whether these versions are suitable. |
| 5 | Wrote `AGENTS.md`, the single rule set. | One source of truth for every coding assistant. |
| 6 | Wrote `CLAUDE.md` as a short pointer instead of a copy. | Two copies of the rules eventually disagree. |
| 7 | Wrote the plan, the state file, the ADR index, the first ADR, and lesson notes. | Planning, progress, and decisions each have their own file. |
| 8 | Checked that the plan has exactly 36 milestones. | Checked by counting, not assumed. |
| 9 | Wrote a completion report and did **not** start Milestone 01. | "Stop after the slice" is part of the contract. |

### Results: files created

```text
portfolio-pilot/
├── AGENTS.md                              ← project contract (the only rule set)
├── CLAUDE.md                              ← pointer: read AGENTS.md + project-state.md
├── README.md                              ← this file
└── docs/
    ├── project-plan.md                    ← 36 milestones with acceptance criteria
    ├── project-state.md                   ← what is done and verified, and what comes next
    ├── decisions/
    │   ├── README.md                      ← how to write ADRs + template + index
    │   └── 0001-architecture-baseline.md  ← first architecture decision
    └── lessons/
        └── 00-project-contract.md         ← teaching notes for this lesson
```

| File | What to look for |
| --- | --- |
| [AGENTS.md](AGENTS.md) | Product scope, the architecture table, the 11 rules, and the five-part completion report format. |
| [CLAUDE.md](CLAUDE.md) | Just two lines. Duplicated rules would drift apart, so it points to `AGENTS.md` instead. |
| [docs/project-plan.md](docs/project-plan.md) | Milestones 01–36 in nine phases (A–I). Each has a scope and an **Accept** line. |
| [docs/project-state.md](docs/project-state.md) | A status table for all milestones, the environment found on this machine, and the latest report. |
| [docs/decisions/README.md](docs/decisions/README.md) | The ADR template and the list of decisions expected later (auth library, news provider, and so on). |
| [docs/decisions/0001-architecture-baseline.md](docs/decisions/0001-architecture-baseline.md) | Why there is one SPA frontend, a separate worker, PostgreSQL as the source of truth, and SSE rather than WebSockets. |
| [docs/lessons/00-project-contract.md](docs/lessons/00-project-contract.md) | Key ideas, an instructor demo, a student exercise, and a common mistake. |

### Results: the completion report

Every milestone ends with the same five-part report, and Prompt 00's was:

- **What works:** the contract, plan, state tracker, and ADR index exist. There is no application
  code, as intended.
- **Changed files:** the seven documentation files above (this README was added afterwards).
- **Check results:** no build or tests exist yet. The assistant confirmed the workspace was empty
  and the plan contains 36 milestones.
- **How to demonstrate it:** see below.
- **Remaining limitations:** the folder was not yet a git repository (the assistant does not
  initialize or commit without approval; it was later committed and pushed on request), and no
  package versions are pinned yet (that is Milestone 01).

### Try it yourself

1. Open a **new** chat with your coding assistant in this folder.
2. Ask: *"What is the next milestone, and what must be true for it to be accepted?"*
3. The assistant should read `CLAUDE.md`, then `AGENTS.md`, then `docs/project-state.md`, and
   answer **"01 — Verify versions and prerequisites"** with that milestone's acceptance criteria.

If it answers correctly without you explaining anything, the contract is working.

### Exercise

Find the rule in `AGENTS.md` that says never to trust a user ID supplied by the model. Then find
Milestones 07, 17, 25, and 29 in the plan and explain how each one enforces that rule.

### Common mistakes

- **Pasting the whole prompt pack at once.** Run one prompt per milestone and check the result
  before moving on.
- **Editing rules in `CLAUDE.md`.** Put project rules in `AGENTS.md` only.
- **Trusting "done" without evidence.** `project-state.md` should contain the commands actually run
  and their real results.

---

## What comes next

Paste **Prompt 01 — Verify versions and prerequisites**. The assistant will choose a compatible,
pinned set of versions (React 19.3+, Vite, Next.js, Prisma, Claude Agent SDK, and others). It will
document them in `docs/versions.md` and add a `.gitignore`, still without writing any application
code.
