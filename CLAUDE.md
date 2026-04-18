# CyberOW – Claude Reference Document

This file is the portable doctrine reference for any Claude session working under the CyberOW framework.
Read this before writing any code, designing any system, or making architectural decisions.

**Author:** github.com/Wadek  
**Repo:** github.com/Wadek/cyberOW  
**License:** MIT — free to use, modify, and distribute including in AI-assisted workflows.

---

## The OW Doctrine (apply to every project)

**OW-1: One-Way Control — Pull over Push**
- Agents pull scoped tasks; control planes do not push high-risk actions by default
- Every automated action must have a defined scope and blast radius
- Default to doing less with explicit approval rather than more without it

**OW-2: One-Way Evidence — Every output produces a ledger entry**
- Every agent action must be logged: what was asked, what tool was called, what was returned, what was approved
- Ledgers are append-only — no updates, no deletes
- Evidence must be human-readable and auditable without additional tooling

**OW-3: One-Way Consolidation — Reduce redundancy deliberately**
- Classify every capability: Canonical / Complementary / Redundant / Bridge-only
- Do not add a new capability if an existing one covers the need
- Prefer depth in one tool over breadth across many

**OW-4: One-Way Value Delivery — Value at every phase boundary**
- Each phase must close with a measurable outcome, not a promise
- Do not defer value realization to a future phase
- Define metrics before building, not after

---

## Agent Role Tiers (apply when building AI-assisted features)

| Role     | Does                                      | Risk        | Required guardrails                          |
|----------|-------------------------------------------|-------------|----------------------------------------------|
| Observer | Read-only: summarize, inventory, report   | Low         | No state changes; cite sources; PII rules    |
| Analyst  | Recommend, prioritize, hypothesize        | Low–Medium  | Evidence ledger; confidence stated; human review |
| Operator | Create tickets, PRs, change plans         | Medium–High | No direct execution; approval gate required  |
| Executor | Apply changes in scoped environment       | High        | Explicit approval; rollback plan; monitoring |

---

## Security Defaults (non-negotiable on every project)

- No personal data (name, email, location) in committed code or git history
- Use `Wadek@users.noreply.github.com` for all public commit identities
- `.env` files always gitignored; `.env.example` committed instead
- Secrets never hardcoded — loaded from environment only
- Least privilege: separate identities/roles for read vs prepare vs execute
- All public repos treated as fully public — no internal refs, no employer details

---

## Evidence-First Pattern (apply to any data model)

When a feature produces outputs that matter (transactions, AI responses, decisions):
1. The output is written to an append-only table before it is acted on
2. The record includes: input, tool/method used, output, timestamp, status
3. No row is ever updated to hide a failed or incomplete state — add a new row instead

---

## How to use this as a project reference

In any project's `CLAUDE.md`, add:
```
Follows CyberOW doctrine: github.com/Wadek/cyberOW — read CLAUDE.md there for principles.
```

When the CyberOW test suite is available (`docs/test-suite-spec.md`), run it against the project
before any major commit or release.

---

## What CyberOW is not

- Not a prescriptive stack — language, framework, and database are project decisions
- Not a compliance checklist — it is a way of thinking about risk, evidence, and autonomy
- Not finished — it grows as pilots surface new patterns (see `docs/pilots/`)
