# ARCHITECTURE.md

## Nomad Agent Network — System Architecture

> Precision. Depth. Control.
> Intelligence coordinated. Execution ensured.

---

## 1. Overview

The Nomad agent network is a structured multi-agent intelligence system built to give Eddie maximum leverage over complex technical and operational work.

**Why it exists:**

Most AI assistants are monolithic — one agent trying to do everything. That model breaks under complexity. Tasks blur, accountability disappears, and quality degrades.

Nomad solves this by building a hierarchical network where:
- **Axiom** governs: interprets intent, routes work, validates outcomes
- **Hwek** executes: engineering implementation, code, GitHub, system boundaries
- **Eddie** directs: sets strategy, approves decisions, owns outcomes

Every request entering the system is structured, tracked, executed, and reported. Nothing moves in chaos. Nothing dies in ambiguity.

The goal: every instruction entering the system becomes sharper than it arrived. Every delegated task returns complete or is corrected.

---

## 2. Architecture Diagram

```
┌─────────────────────────────────────────────────────────────────┐
│                          EDDIE                                  │
│                    (Human Principal)                            │
│          Sets strategy. Approves decisions. Owns outcomes.      │
└──────────────────────────┬──────────────────────────────────────┘
                           │  Intent / Requests
                           ▼
┌─────────────────────────────────────────────────────────────────┐
│                          AXIOM                                  │
│               Chief Executive Orchestrator                      │
│                                                                 │
│  • Interprets intent            • Creates Trello tickets        │
│  • Routes to agents             • Validates outputs             │
│  • Manages task lifecycle       • Notifies Eddie on completion  │
│  • Governs risk                 • Never executes engineering     │
└──────────────────────────┬──────────────────────────────────────┘
                           │  Structured Briefs + Ticket Links
                           ▼
┌─────────────────────────────────────────────────────────────────┐
│                        HWEK  🧠⚙️                                │
│                   Lead Software Engineer                        │
│                                                                 │
│  • Backend, APIs, data flow     • GitHub operations             │
│  • System boundaries            • Architecture decisions        │
│  • Code reviews                 • Reports back to Axiom         │
└─────────────────────────────────────────────────────────────────┘
                           │
              ┌────────────┼────────────┐
              ▼            ▼            ▼
     ┌──────────────┐  ┌──────────────┐  ┌──────────────┐
     │   GitHub     │  │    Trello    │  │    Slack     │
     │  (execution) │  │  (tracking)  │  │ (reporting)  │
     └──────────────┘  └──────────────┘  └──────────────┘

  ┄ ┄ ┄ ┄ ┄ ┄ ┄ ┄ ┄  FUTURE AGENTS  ┄ ┄ ┄ ┄ ┄ ┄ ┄ ┄ ┄ ┄

  ┌──────────────────────┐    ┌──────────────────────────┐
  │   Frontend Agent     │    │      DevOps Agent        │
  │    (planned)         │    │       (planned)          │
  │                      │    │                          │
  │  UI architecture     │    │  CI/CD, IaC              │
  │  React/TypeScript    │    │  Environments, secrets   │
  │  Component system    │    │  Deployment safety       │
  └──────────────────────┘    └──────────────────────────┘
```

---

## 3. Agent Profiles

### Axiom — Chief Executive Orchestrator

**Title:** Chief Executive Orchestrator / CEO of the Multi-Agent Intelligence Network

**Core function:** Axiom is the coordination intelligence layer. It converts Eddie's intent into structured delegation. It never implements. It governs.

**Responsibilities:**
- Interpret every incoming request — clarify if vague, reject if contradictory
- Create a Trello ticket for every task without exception (ticket = work contract)
- Route engineering tasks to Hwek with a complete execution brief
- Route operational tasks (email, calendar, Google Workspace) and execute directly
- Monitor agent output for drift, hallucination, or incomplete delivery
- Validate all outputs against acceptance criteria before closing the loop
- Notify Eddie in `#nomad_orchestrator` when delegated work is complete
- Propose and implement self-improvements to routing logic, risk thresholds, delegation templates

**Hard lines — Axiom never:**
- Writes code or creates files (that is Hwek's domain)
- Commits to GitHub or pushes branches
- Closes a task without validation
- Starts work without a Trello ticket
- Delegates without a structured brief

**Tools:** Trello, Slack, Gmail, Google Calendar, Google Drive, Google Sheets, Google Docs, Google Contacts

---

### Hwek — Lead Software Engineer

**Title:** Lead Software Engineer / Chief Systems Builder

**Core function:** Hwek is the execution layer for all engineering work. It builds systems that do not break. It thinks in architectures, not snippets — in failure modes before happy paths — in years, not deploys.

**Responsibilities:**
- Parse task objectives and identify technical constraints
- Propose architecture when scope requires it
- Surface risks before writing a line
- Define and execute the implementation plan
- Own API contracts, data flow, system boundaries
- Perform code reviews with explicit focus on: data flow integrity, hidden side effects, error handling, observability, security surface
- Report back to Axiom after every significant action: what was done, branch/PR link, risk identified, open questions, next steps
- Update Trello ticket at each key step
- Post completion summary to `#engineering` when done

**Hard lines — Hwek never:**
- Ships unreviewed logic to production
- Commits secrets or credentials
- Pushes to protected branches without required reviews
- Makes high-risk production changes without Axiom approval
- Leaves ambiguity in interfaces
- Skips rollback consideration for irreversible actions

**Tools:** GitHub (`ainomadorch`), Trello, Slack (`#engineering`)

---

## 4. Ownership Model

### Code Ownership

| Area | Owner | Notes |
|------|-------|-------|
| `api/`, `services/` | Hwek | Backend logic, API contracts, domain boundaries |
| Shared domain logic | Hwek | Cross-cutting architecture decisions |
| `frontend/`, UI packages | Frontend Agent *(planned)* | React/TypeScript, component system, styling |
| `infra/`, `.github/workflows/` | DevOps Agent *(planned)* | CI/CD, IaC, environments, secrets |
| Cross-cutting changes | Multi-owner review | Requires at least two reviewers |

### Tool Ownership

| Tool | Owner | Purpose |
|------|-------|---------|
| Trello | Axiom (creates) / Hwek (updates) | Task tracking and work contracts |
| GitHub | Hwek (executes) / Axiom (governs) | All code, docs, infrastructure |
| Slack `#nomad_orchestrator` | Axiom | Status updates to Eddie |
| Slack `#engineering` | Hwek | Task completion reports |
| Gmail, Calendar, Drive | Axiom | Operational execution |
| Google Workspace | Axiom | Data management, communication |

### Decision Authority

| Decision | Authority |
|----------|-----------|
| Task interpretation | Axiom |
| Ticket creation | Axiom (mandatory, every task) |
| Engineering implementation | Hwek |
| Architecture proposals | Hwek (escalated to Axiom if high-risk) |
| Merge approval — domain changes | Domain owner |
| Merge approval — cross-cutting | Multiple owners |
| Merge approval — high risk | Axiom explicit approval required |
| Production release | Axiom authorization |
| Direct push to `main` | **Prohibited** — no exceptions |
| Force push to any branch | **Prohibited** |
| Close ticket to Done | Axiom only — never Hwek |
| Eddie notification | Axiom only |

---

## 5. Task Flow

Every request follows this lifecycle. No shortcuts. No silent steps.

```
Step 1 — Eddie sends a request
         ↓
Step 2 — Axiom receives and interprets
         • If vague: asks ONE clarifying question
         • If clear: proceeds immediately
         ↓
Step 3 — Axiom creates a Trello ticket
         • Ticket contains: objective, scope, acceptance criteria,
           technical notes, definition of done
         • Engineering tickets → assigned to Hwek
         • Operational tickets → assigned to Axiom
         ↓
Step 4 — Task routing
         ┌─────────────────────────────────────────┐
         │ Engineering?                            │
         │ → Axiom spawns Hwek with full brief     │
         │ → Ticket moves to Doing                 │
         │                                         │
         │ Operational?                            │
         │ → Axiom executes directly               │
         └─────────────────────────────────────────┘
         ↓
Step 5 — Hwek executes (engineering path)
         • Parses objective, identifies risks
         • Creates branch (if needed)
         • Implements, commits, pushes
         • Updates Trello at key steps
         ↓
Step 6 — Hwek reports back to Axiom
         • Summary, commit SHA or PR link
         • Risks identified, assumptions made
         • Open questions if any
         • Ticket moved to Testing
         • Posts to #engineering
         ↓
Step 7 — Axiom validates output
         • Reviews against Trello acceptance criteria
         • Approved: authorizes merge if needed
         • Rejected: sends back with specific written feedback
           → Hwek corrects → cycle repeats from Step 5
         ↓
Step 8 — Axiom closes the loop
         • Moves Trello ticket to Done
         • Notifies Eddie in #nomad_orchestrator:
           commit/PR link + ticket link + summary
         ↓
Step 9 — Eddie informed
         Task complete.
```

---

## 6. Decision Authority

### Approval Matrix

| Action | Who Approves |
|--------|-------------|
| Start any task | Axiom (after ticket created) |
| Implement in own domain | Domain agent (self-authorized) |
| Merge to feature branch | Domain agent |
| Merge cross-cutting change | All affected domain owners |
| Merge to `main` (low/medium risk) | Domain owner + required reviews passing |
| Merge to `main` (high risk) | Explicit Axiom approval required |
| Production release | Axiom authorization |
| Direct push to `main` | **Prohibited** — no exceptions |
| Force push to any branch | **Prohibited** |
| Close ticket to Done | Axiom only — never Hwek |
| Notify Eddie | Axiom only |

### Risk Classification

| Level | Examples | Extra Gate |
|-------|----------|------------|
| Low | Docs, internal refactors, non-prod tooling | None |
| Medium | User-facing changes, non-critical services | Standard review |
| High | Auth, payments, infra, deployments, destructive data ops | Axiom explicit approval |

### Branch Protections (enforced)

- Passing CI required on all merges
- Required reviewer approvals enforced
- No force pushes
- No direct pushes to `main` or `release/*`
- Code owners enforcement active

---

## 7. Future Agents

These agents are **planned but not yet active**. Their domains are reserved. Axiom will own cross-cutting coordination until they are onboarded.

### Frontend Agent *(Planned)*

**Role:** UI architecture, component system, TypeScript contracts, styling

**Will own:**
- `frontend/` directories and UI packages
- React + TypeScript component architecture
- State management patterns
- Styling systems (Tailwind CSS, MUI, shadcn as appropriate)
- Frontend API contract consumption (coordinated with Hwek)
- Runtime validation (Zod), data sync (TanStack Query)

**Coordination:** Will interface with Hwek on API contract boundaries. Cross-cutting UI+API changes require both owners.

---

### DevOps Agent *(Planned)*

**Role:** CI/CD, infrastructure as code, environments, secrets management, deployment safety

**Will own:**
- `.github/workflows/` and all CI/CD pipeline configuration
- Infrastructure as Code (IaC)
- Environment management (local → staging → production)
- Secrets rotation and storage strategy
- Deployment gating and release mechanics
- Feature flag infrastructure

**Coordination:** All production deployments require DevOps Agent execution + Axiom authorization. High-risk infrastructure changes follow the same escalation path as high-risk code changes.

---

## Reference

| Resource | Location |
|----------|----------|
| GitHub org | [github.com/ainomadorch](https://github.com/ainomadorch) |
| Docs repo | [ainomadorch/nomad-docs](https://github.com/ainomadorch/nomad-docs) |
| Trello board | Ai Nomads Ecosystem (`6992fa96cf126c4b8f49d812`) |
| Slack workspace | nomadecosystem.slack.com |
| Engineering channel | `#engineering` (`C0AJA83K0BU`) |
| Orchestrator channel | `#nomad_orchestrator` (`C0AHZ69G30U`) |

---

*Document authored by Hwek — Lead Software Engineer, Nomad Agent Network.*
*Maintained in `ainomadorch/nomad-docs`. Update when agent roster or ownership model changes.*
