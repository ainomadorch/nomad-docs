# CONTRIBUTING.md

How agents contribute to the Nomad framework.

This document defines the standards, protocols, and authority model for all contributions to `ainomadorch` repositories. Every agent must follow these rules — no exceptions.

---

## 1. Ticket Protocol

**A Trello ticket is required before any work begins.**

No branch. No commit. No code. No ticket = no work.

**Board:** Ai Nomads Ecosystem (`6992fa96cf126c4b8f49d812`)

### Ticket Lifecycle

```
Backlog → Doing → Testing → Done
```

| Stage | Trigger |
|---|---|
| **Backlog** | Axiom creates ticket, assigns to agent |
| **Doing** | Agent spawned, work starts |
| **Testing** | Agent reports back — work is complete, awaiting Axiom review |
| **Done** | Axiom approves — mandatory before notifying Eddie |

**Hwek never moves a ticket to Done — that is Axiom's decision.**

### Required Ticket Updates

1. **When work starts** — comment: `Starting work. Branch: <branch>. Approach: <one sentence>.`
2. **During work** — comment on significant steps (branch created, key decision, blocker)
3. **When complete** — comment with: summary of what was done, commit SHA or PR link, deviations from brief, output confirming result
4. **Move to Testing** after the completion comment

---

## 2. Agent Assignment Rules

Assignment is set at ticket creation, before any agent is spawned.

| Task Type | Assigned To |
|---|---|
| Engineering tasks | **Hwek** |
| Operational tasks (email, calendar, research, Slack) | **Axiom** |

- Engineering tickets → assigned to Hwek, created in **Backlog**
- Operational tickets → assigned to Axiom, created in **Overhead**

Do not reassign after creation without explicit Axiom approval.

---

## 3. Branching Strategy

**Protected branches:** `main` (always deployable), `release/*` or `prod` if needed.

**No direct pushes to `main`.** Ever.

### Working Branch Patterns

```
feature/<area>-<short-desc>
fix/<area>-<short-desc>
infra/<short-desc>
chore/<short-desc>
```

### Area Examples

`api` · `ui` · `auth` · `data` · `pipelines` · `deploy` · `billing`

**Examples:**
- `feature/api-add-s3-upload`
- `fix/auth-token-expiry`
- `infra/configure-iam-glue`
- `chore/update-dependencies`

---

## 4. Commit Format

```
type(scope): short description

Why this change exists
Key notes or tradeoffs
```

### Valid Types

| Type | Use For |
|---|---|
| `feat` | New feature |
| `fix` | Bug fix |
| `perf` | Performance improvement |
| `refactor` | Code restructure (no behavior change) |
| `test` | Adding or updating tests |
| `chore` | Maintenance, dependency updates |
| `docs` | Documentation only |
| `infra` | Infrastructure changes |
| `ci` | CI/CD pipeline changes |

**Rules:**
- No `wip` as a final commit
- No `updates` or vague messages
- Body must explain *why*, not just what
- Scope must match the area being changed

---

## 5. PR Requirements

Every PR opened by any agent must include:

| Field | Required |
|---|---|
| **Objective** | What this PR accomplishes |
| **Summary of changes** | What was added, removed, or changed |
| **Risk level** | Low / Medium / High |
| **Testing evidence** | How it was tested, output or logs |
| **Rollback plan** | Required for High risk PRs |
| **Owner reviews** | Correct domain owners requested |

### Risk Levels

| Level | Examples |
|---|---|
| **Low** | Docs, internal refactors, non-prod tooling |
| **Medium** | User-facing changes, non-critical services |
| **High** | Auth, payments, infra, deployments, destructive data ops |

High risk PRs **must escalate to Axiom** before merge.

---

## 6. Merge Authority

| Action | Authority |
|---|---|
| Merge Low / Medium risk PRs | Domain owner approval |
| Merge High risk PRs | **Axiom approval required** |
| Direct push to `main` | **Never permitted** |
| Domain changes | Domain owner must approve |
| Cross-cutting changes | Minimum two reviewers required |

**Axiom governs. Agents execute within delegated authority.**

If there is a conflict between agents on a PR: each agent states tradeoff in one paragraph → Axiom decides → decision is written into the PR.

---

## Enforcement

These are not guidelines. They are operational contracts.

Violations block merges and escalate to Axiom.

> The network scales by discipline, not heroics.
