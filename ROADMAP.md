# ROADMAP.md — Nomad Agent Network Expansion

> Intelligence coordinated. Execution ensured.
> This document defines the planned expansion of the Nomad agent network — upcoming agents, their ownership domains, and the build order that governs activation.

---

## Current State

The Nomad network is operational with two active agents. The system is stable, tracked, and disciplined. Every task is contracted through Trello. Every engineering action is executed through GitHub. Every outcome is reported to Eddie.

The foundation holds. Now we build on it.

---

## Phase 1 — Active

### Axiom — Chief Executive Orchestrator

**Status:** Active ✅

**Role:** Axiom is the coordination intelligence layer. It converts Eddie's intent into structured delegation. It governs — it never implements.

**What Axiom owns:**
- Task interpretation and routing
- Trello ticket creation for every task (no exceptions)
- Delegation of engineering tasks to Hwek with full execution briefs
- Direct execution of operational tasks (Gmail, Calendar, Google Workspace)
- Output validation against acceptance criteria
- Eddie notification on all completed work
- Risk governance and escalation arbitration

**Tools:** Trello, Slack, Gmail, Google Calendar, Google Drive, Google Sheets, Google Docs, Google Contacts

**What is live and stable:**
- Trello-based task lifecycle (Backlog → Doing → Testing → Done)
- Structured Hwek delegation via `sessions_spawn` with execution briefs
- Operational task execution (email, calendar, research) by Axiom directly
- Eddie notification protocol via `#nomad_orchestrator`
- Escalation gates for high-risk decisions

---

### Hwek — Lead Software Engineer 🧠⚙️

**Status:** Active ✅

**Role:** Hwek is the execution layer for all engineering work. Systems that do not break. Architecture before code. Failure modes before happy paths.

**What Hwek owns:**
- `api/`, `services/`, shared domain logic
- API contract definition and enforcement
- Data flow architecture and system boundary decisions
- GitHub operations (branches, commits, PRs, code review)
- Cross-cutting architecture reviews (performance, security, system boundaries)
- Trello ticket updates throughout execution
- Structured reports back to Axiom after every significant action

**Tools:** GitHub (`ainomadorch`), Trello, Slack (`#engineering`)

**What is live and stable:**
- GitHub branching strategy (`feature/`, `fix/`, `infra/`, `chore/`)
- Commit standards enforced (`type(scope): description`)
- PR lifecycle with risk classification (Low / Medium / High)
- Trello ticket update protocol (start comment → progress comments → completion comment)
- `#engineering` completion reports with commit SHA and ticket link
- Mandatory memory writes after every task

---

## Phase 2 — Frontend Agent

**Status:** Planned — not yet active

### Role and Title

**Title:** Lead Frontend Engineer
**Codename:** TBD at activation

**Core function:** Own the full UI layer. Architecture, components, contracts, styling, state, and data sync. Move fast inside typed, predictable systems. Never leave visual entropy.

---

### Ownership Domain

| Area | Details |
|------|---------|
| `frontend/` directories | All UI packages, apps, and components |
| React + TypeScript architecture | Component-driven, strongly typed, deterministic |
| Component system | Reusable, composable, pattern-driven |
| Styling | Tailwind CSS first; MUI or shadcn where system benefits |
| State management | Predictable, explicit — no implicit global mutations |
| Runtime validation | Zod — typed schemas across API boundaries |
| Data synchronization | TanStack Query — server state, caching, invalidation |
| Frontend API contract consumption | Coordinated with Hwek on every boundary |

The Frontend Agent owns everything inside `frontend/`. No other agent modifies these directories without explicit Frontend Agent review.

---

### Tools

- **GitHub** — branches, commits, PRs in `frontend/` domain
- **Trello** — ticket updates throughout execution, moves to Testing on completion
- **Slack `#engineering`** — completion reports, blocker escalation

---

### Coordination Interface

**With Hwek:**
- API contract boundaries are a shared interface. Neither agent ships a breaking change without the other reviewing it.
- All cross-cutting UI+API changes require both Hwek (API side) and Frontend Agent (consumption side) as PR reviewers.
- Contract-first approach: API shape is agreed before implementation begins on either side.
- When both owners have conflicting priorities: each states the tradeoff in one paragraph → Axiom decides → decision written into PR.

**With Axiom:**
- Frontend Agent reports directly to Axiom on task completion
- High-risk changes (auth flows, billing UI, destructive user actions) require Axiom explicit approval before merge
- Eddie notification always goes through Axiom — never directly from the Frontend Agent

---

### Activation Criteria

The Frontend Agent is considered active and onboarded when **all** of the following are true:

- [ ] At least one `frontend/` directory exists in a repo under `ainomadorch` with defined TypeScript structure
- [ ] API contract boundary documentation exists (how the frontend consumes Hwek's APIs)
- [ ] Frontend Agent has been tested end-to-end: receives brief from Axiom → executes task → commits to correct branch → updates Trello → posts to `#engineering` → reports back
- [ ] At least one PR has been reviewed by both Hwek and Axiom before merge
- [ ] Axiom has verified the agent correctly escalates high-risk changes before proceeding
- [ ] Coordination handshake with Hwek is live: a shared API contract has been agreed and committed to the repo

---

## Phase 3 — DevOps Agent

**Status:** Planned — not yet active

### Role and Title

**Title:** Lead DevOps Engineer
**Codename:** TBD at activation

**Core function:** Own the delivery layer. Pipelines, environments, secrets, deployments, release mechanics. Nothing reaches production without DevOps Agent execution. Nothing high-risk reaches production without Axiom authorization.

---

### Ownership Domain

| Area | Details |
|------|---------|
| `.github/workflows/` | All CI/CD pipeline configuration — lint, test, build, deploy |
| Infrastructure as Code (IaC) | Cloud resources, provisioning, environment definitions |
| Environment management | Local → Staging → Production promotion chain |
| Secrets rotation | Managed secret stores, rotation schedules, scoped CI credentials |
| Deployment gating | Controls what merges to what, when, and under what conditions |
| Release mechanics | Trunk-based with staged promotion; production is always a manual approval step |
| Feature flag infrastructure | Flag defaults safe, must be removable, behavior must be tested before removal |

The DevOps Agent owns everything that controls how code reaches a running environment. No other agent modifies `.github/workflows/` or IaC without explicit DevOps Agent review.

---

### Tools

- **GitHub** — CI/CD configuration, IaC commits, deployment workflows
- **Trello** — ticket updates, moves to Testing on completion
- **Slack `#engineering`** — deployment announcements, incident escalation

---

### Coordination Interface

**With Hwek:**
- DevOps Agent controls the delivery pipeline. Hwek controls what gets delivered.
- New service or infrastructure changes require DevOps Agent to build the corresponding pipeline before it ships.
- Hwek surfaces new dependency or environment requirements; DevOps Agent owns their implementation.

**With Frontend Agent:**
- Build and deploy pipelines for `frontend/` are owned by DevOps Agent.
- Frontend Agent flags environment or CDN requirements; DevOps Agent implements and validates.

**With Axiom:**
- All production deployments require: DevOps Agent execution + Axiom authorization.
- High-risk infrastructure changes (secrets rotation, environment configuration, IaC destructive ops) follow the same escalation path as high-risk code changes.
- DevOps Agent never promotes to production autonomously — Axiom authorization is always required.
- Incident response: DevOps Agent leads containment; Axiom decides on rollback or escalation to Eddie.

---

### Activation Criteria

The DevOps Agent is considered active and onboarded when **all** of the following are true:

- [ ] At least one repository under `ainomadorch` has a working CI pipeline (lint → test → build) defined in `.github/workflows/`
- [ ] Staging environment exists and is reachable with automated deployment from `main`
- [ ] Secrets management strategy is documented and at least one secret is stored in a managed store (not hardcoded)
- [ ] Production deployment requires explicit Axiom approval — this gate is enforced by pipeline configuration, not convention alone
- [ ] DevOps Agent has been tested end-to-end: receives brief → modifies pipeline → commits → updates Trello → posts to `#engineering` → reports back to Axiom
- [ ] Axiom has verified the agent will not promote to production without authorization
- [ ] Coordination handshake with Hwek is live: at least one successful deployment of Hwek's code through the DevOps Agent pipeline

---

## Build Order Rationale

### Why Frontend Before DevOps

**1. Product leverage comes first.**
The Frontend Agent directly extends the product surface — it ships user-visible output. Before deployment infrastructure is formalized, we can still ship manually to staging. That is acceptable at this scale. Delaying product execution to build the delivery layer first inverts the priority.

**2. Frontend depends less on DevOps than DevOps depends on product.**
The DevOps Agent needs something to deploy. A mature pipeline for an empty system is waste. Building the Frontend Agent first creates real deployment targets that make the DevOps work concrete and scoped — not abstract.

**3. Hwek + Frontend Agent unlocks the full product layer.**
The API contract boundary between Hwek and the Frontend Agent is the most high-leverage coordination point in the current network. Establishing it early forces discipline in API design, which benefits everything that comes after — including what the DevOps Agent deploys.

**4. Risk profile.**
Frontend changes are more reversible than infrastructure changes. Learning how to coordinate multi-agent PR reviews on UI work is a lower-stakes proving ground before the DevOps Agent begins managing secrets, environments, and production access.

### Dependencies Between Agents

```
Axiom
  └── Hwek (active)
        └── Frontend Agent (Phase 2)
              └── DevOps Agent (Phase 3)
```

- DevOps Agent cannot be properly activated until there is a product to deploy (requires Hwek + Frontend Agent to have meaningful scope)
- Frontend Agent cannot be properly activated until Hwek's API contract practices are stable
- All agents depend on Axiom's task lifecycle remaining disciplined — the Trello → spawn → report → validate loop must hold

### Risk and Leverage Considerations

| Phase | Risk Level | Leverage |
|-------|-----------|---------|
| Phase 1 (Axiom + Hwek) | Low — stable, well-scoped | High — every future agent builds on this foundation |
| Phase 2 (Frontend) | Medium — UI is user-facing | High — ships visible product value |
| Phase 3 (DevOps) | High — controls production access | Extreme — required for sustainable release velocity |

DevOps Agent carries the highest activation risk because it controls secrets, environments, and production gates. It activates last because by then the coordination patterns, PR discipline, and review norms are established and load-tested across two prior agent onboardings.

---

## Phase 4+ — Future Expansion

**Status:** Not yet defined

This section is reserved for agents that have not yet been scoped. No codenames. No premature architecture. When Eddie defines new strategic domains that require dedicated agent ownership, they will be designed here before activation begins.

---

### Principles That Will Govern Future Agent Onboarding

Every future agent — regardless of domain — must satisfy these conditions before activation:

**1. Domain must be clearly bounded.**
If two agents could reasonably claim ownership of the same file or system, the boundary is not clear enough. Define it before activating the agent.

**2. Coordination interfaces must be explicit.**
Every new agent must define: who it coordinates with, on what decisions, and what the escalation path is. "Works with Hwek" is not a coordination interface. "Cross-cutting API+UI changes require both owners as reviewers before merge" is.

**3. Activation criteria must be testable.**
A checklist that cannot be verified is not a checklist. Each criterion must produce a binary pass/fail answer. No subjective gates.

**4. Axiom governs until activation is complete.**
Any domain not yet owned by a specialized agent defaults to Axiom coordination. Axiom does not execute the work — but it holds the boundary until the right agent is ready.

**5. One agent per domain.**
Shared ownership without clear arbitration is ambiguity dressed as collaboration. Domains may overlap at boundaries — but a primary owner must be declared for every file and system.

**6. High-risk domains activate last.**
If a new agent will control production systems, secrets, financial data, or user authentication — it activates after lower-risk agents have established coordination discipline in the network.

**7. New agents are proposed by Axiom, approved by Eddie.**
Agent network expansion is a strategic decision. Axiom may identify the need and propose the design. Eddie approves before any activation begins.

---

## Reference

| Resource | Location |
|----------|----------|
| Architecture doc | [`ARCHITECTURE.md`](./ARCHITECTURE.md) |
| GitHub org | [github.com/ainomadorch](https://github.com/ainomadorch) |
| Docs repo | [ainomadorch/nomad-docs](https://github.com/ainomadorch/nomad-docs) |
| Trello board | Ai Nomads Ecosystem (`6992fa96cf126c4b8f49d812`) |
| Slack workspace | nomadecosystem.slack.com |
| Engineering channel | `#engineering` (`C0AJA83K0BU`) |
| Orchestrator channel | `#nomad_orchestrator` (`C0AHZ69G30U`) |

---

*Document authored by Hwek — Lead Software Engineer, Nomad Agent Network.*
*Maintained in `ainomadorch/nomad-docs`. Update when agent roster, ownership model, or activation criteria change.*
