# Nomad Agentic Framework

> *A disciplined multi-agent intelligence network built for orchestration, delegation, and execution at scale.*

---

## Overview

The **Nomad Agentic Framework** is a structured multi-agent system designed to convert intent into coordinated execution across specialized AI agents. It operates through a clear hierarchy: a central orchestrating intelligence governs a network of domain-specialized subagents, each operating within defined authority boundaries.

The system is built on three principles:

- **Clarity over compliance** — Every task is sharpened before execution.
- **Delegation over centralization** — The right agent handles the right work.
- **Validation over assumption** — No task is complete until verified.

---

## Architecture

```
Eddie (Human Principal)
        │
        ▼
   ┌─────────┐
   │  Axiom  │  ← Chief Executive Orchestrator
   └────┬────┘     Governs the network. Routes intent. Enforces discipline.
        │
        ▼
   ┌─────────┐
   │  Hwek   │  ← Lead Software Engineer
   └─────────┘     API contracts · Data flow · System boundaries · GitHub
```

> Additional agents (Frontend, DevOps) are in the roadmap.

---

## Agents

### Axiom — Chief Executive Orchestrator

Axiom is the top-level intelligence layer. It does not execute; it directs.

**Responsibilities:**
- Interpret user intent and reduce it to structured objectives
- Route tasks to the appropriate subagent
- Define success criteria before delegation
- Validate outputs against acceptance criteria
- Close the loop — no task is silent-failed

**Persona:** Calm. Precise. Slightly confrontational when necessary. Reality wins.

---

### Hwek — Lead Software Engineer

Hwek is the primary execution agent for backend and infrastructure work.

**Responsibilities:**
- Backend and API implementation
- GitHub operations (branches, commits, PRs, reviews)
- Data pipeline architecture
- Cross-system boundary enforcement

**Scope:** `api/`, `services/`, shared domain logic, data flows

---

## Workflow

Every request follows this lifecycle:

```
1. Intent received by Axiom
2. Axiom interprets + clarifies (if needed)
3. Trello ticket created — work contract established
4. Hwek (or relevant agent) spawned with full context
5. Agent executes and reports back
6. Axiom reviews output against acceptance criteria
7. On approval: Eddie notified in #nomad_orchestrator
8. Ticket closed. Loop complete.
```

**No task moves without a ticket. No ticket closes without validation.**

---

## Tooling

The framework operates through **OpenClaw**, a personal AI infrastructure platform.

| Category | Tool |
|---|---|
| Orchestration | OpenClaw sessions, subagents |
| Communication | Slack (`#nomad_orchestrator`, `#engineering`) |
| Project Management | Trello |
| Version Control | GitHub (`ainomadorch`) |
| Email / Calendar | Google Workspace (`ruizeduardo21@gmail.com`) |
| Search | Web search + web fetch |

---

## Standards

### Ticket Creation

Every Trello ticket must include:
- **Context** — Why this work exists
- **Objective** — Expected outcome
- **Scope** — What's in, what's out
- **Acceptance Criteria** — Binary, testable conditions
- **Definition of Done**

Title format: `[Project][Feature] Action + Object`

---

### GitHub Workflow

**Branching:**
- `feature/<area>-<short-desc>`
- `fix/<area>-<short-desc>`
- `infra/<short-desc>`

**Commit format:**
```
type(scope): short description

Why this change exists
Key notes or tradeoffs
```

**PR requirements:** Objective, change summary, risk level (Low/Medium/High), testing evidence, rollback plan for High risk.

**Merge authority:** Axiom approval required for High risk merges. No direct pushes to `main`.

---

### Risk Classification

| Level | Examples |
|---|---|
| Low | Docs, internal refactors, non-prod tooling |
| Medium | User-facing changes, non-critical services |
| High | Auth, payments, infra, deployments, destructive data ops |

---

## Reporting Format

When a delegated task completes, Axiom reports to Eddie in `#nomad_orchestrator`:

```
*[Task Complete]* — short title

> What was built and why

• Hwek completed: <summary>
• PR: <link>
• Ticket: <link>
• Status: Merged / Pending review
```

---

## Self-Improvement

The framework is designed to evolve. Axiom monitors for:
- Delegation errors and routing failures
- Ambiguity patterns across tasks
- Subagent drift or scope creep
- Process inefficiencies

Improvements are proposed explicitly, reviewed by Eddie, and documented in system files before implementation. **No silent mutations.**

---

## Directory Structure

```
workspace/
├── AGENTS.md        — Agent network conventions and delegation rules
├── SOUL.md          — Axiom's core persona and communication doctrine
├── IDENTITY.md      — Self-improvement and meta-cognition framework
├── USER.md          — Context about Eddie (the human principal)
├── TOOLS.md         — Environment-specific tool config (Slack, GitHub, GWS)
├── HEARTBEAT.md     — Periodic task checklist for proactive monitoring
├── MEMORY.md        — Long-term curated memory
└── memory/          — Daily session logs (YYYY-MM-DD.md)
```

---

## Contact

- **Human Principal:** Eddie — `ruizeduardo21@gmail.com`
- **Primary Slack:** `#nomad_orchestrator`
- **Engineering Slack:** `#engineering`
- **GitHub Org:** `ainomadorch`

---

*The network scales by discipline, not heroics.*
