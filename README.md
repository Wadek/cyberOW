# CyberOW – One-Way Operating Way for AI-First Cybersecurity

**A practical operating model for safe, evidence-driven AI in cybersecurity**

**Author:** [github.com/Wadek](https://github.com/Wadek)  
**License:** MIT — free to use including in AI-assisted workflows and Claude integrations.  
**For Claude users:** Read [`CLAUDE.md`](./CLAUDE.md) for a portable doctrine reference you can apply to any project.

CyberOW is an AI-first cybersecurity operating framework designed to improve speed, consistency, and resilience while reducing single points of failure and key-person risk.

It decomposes cyber work into standard, repeatable **work units** that can be assisted or executed by AI agents under strict **One-Way** constraints, delivering measurable value at the end of every phase.

## Executive Summary

CyberOW focuses on Technology, Data, and AI acceleration through resilient and secure practices.  
We deliberately avoid assuming that current architecture or organizational boundaries are “correct.”

**What changes:**  
Cyber work is broken into standard, repeatable work units that AI agents can assist or execute with clear human approval gates.

**What stays safe:**  
Agents operate under “One-Way” constraints: controlled connectivity, evidence-first outputs, and staged automation.

**What is valuable:**  
Measurable value at the end of each phase (cycle time reduction, quality uplift, audit-ready evidence packs) — not deferred benefits. This is a process
followed and we ensure value at each defined phase end.

**What the organization gains:**  
Reduced dependence on individual expertise by capturing institutional knowledge as policies, playbooks, and evidence-linked workflows. We hope to codify
the entire Cyber Security process.

## The “OW” Doctrine – Core Design Principles

CyberOW uses “OW” in two deliberate senses:  
- **One-Way** as a security architecture property (safe, controlled, pull-based)  
- **Operating Way** as a repeatable delivery doctrine

### The Four One-Ways

**OW-1: One-Way Control (Pull > Push)**  
Agents are designed so the control plane does not initiate high-risk actions by default. Agents pull scoped tasks, execute in controlled contexts, and return results + evidence. Staged Autonomy becomes the standard of practice.

**OW-2: One-Way Evidence (Every output produces a ledger)**  
Every agent output must be evidence-linked: source references, tool calls, assumptions, and decision rationale are captured in an immutable evidence ledger. This enables auditability, repeatability, and defensible governance.

**OW-3: One-Way Consolidation (Reduce redundancy deliberately)**  
Every capability is classified as **Canonical**, **Complementary**, **Redundant**, or **Bridge-only**. This makes overlaps explicit and drives a rational consolidation roadmap toward a small number of well-integrated ecosystems.

**OW-4: One-Way Value Delivery**  
Each phase must close with measurable operational outcomes (cycle time, quality, coverage, resilience metrics). Value realization is mandatory at phase boundaries.

## Work Decomposition

CyberOW starts by cataloging operational work across six functional **Cyber Stacks**:

- **Govern**
- **Identify**
- **Protect**
- **Detect**
- **Respond**
- **Recover**

Each category is decomposed into:
- Work units (verbs + inputs + outputs)
- Decision points (who approves what, under which conditions)
- Evidence requirements (what must be recorded)
- Automation boundary (assist, prepare, execute)

### Standardized Agent Roles

| Role       | What it does                                      | Risk Level     | Typical Guardrails                              |
|------------|---------------------------------------------------|----------------|-------------------------------------------------|
| Observer   | Read-only summarization, inventory, mapping, reporting | Low            | No actions; evidence citations; PII rules       |
| Analyst    | Hypothesis generation, prioritization, recommended next steps | Low-Medium     | Evidence ledger; confidence; human review       |
| Operator   | Creates tickets/PRs/change plans; prepares remediation | Medium-High    | No direct execution; approvals; least privilege |
| Executor   | Applies changes in scoped domains                 | High           | Explicit approvals; environment scoping; rollback plans; monitoring |

## Phased Delivery (Value at the end of each phase)

| Phase | Focus                        | Key Deliverables (examples)                          | Value Realized (examples)                     |
|-------|------------------------------|------------------------------------------------------|-----------------------------------------------|
| 1     | Read-Only Acceleration       | Policy assistant, Evidence Ledger, initial Reality Graph | Reduced SME bottlenecks, faster assessments   |
| 2     | Operator Mode                | Ticket/PR generators, investigation copilots         | Cycle-time reduction, improved repeatability  |
| 3     | Supervised Execution         | Narrow-scope automation with verification/rollback   | Lower incident duration, higher control effectiveness |
| 4     | Sandbox Autonomy             | Digital twin simulations, controlled advanced testing | Proactive risk reduction, faster learning loops |

## Core Architecture

**Mythos Core**  
Security Reality Graph + Evidence Ledger (immutable record of inputs, tool calls, outputs, approvals, and outcomes).

**MILK Extension** (Mythos Integration & Ledger Kernel)  
Safe scaffolding layer for higher-capability models with controlled environments, one-way execution patterns, and explicit approval gates. Not all organizations can safely make use of higher-capability models and we aim to provide a moving entrypoint into the operating model.

**Key Guardrails**
- Least privilege for agent identities (separate identities for read vs prepare vs execute)
- Explicit approval gates for any action that changes state
- Full logging and monitoring for all agent tool calls and data access
- Content rules for sensitive data enforced at ingress points
- Staged autonomy with clear blast-radius limitations

## Governance & Operating Cadence

- Organizational Dependent, a simple model as a starting point is documented.

- **Steering** (monthly) – Prioritize roadmap, resolve cross-domain blockers
- **Architecture & Controls** (bi-weekly) – Approve standards, guardrails, evidence requirements
- **Use Case Review** (weekly) – Review pilots and manage risk
- **Ops Feedback Loop** (weekly) – Capture pain points and refine work units / prompts

**Example Metrics**
- Cycle time (triage, remediation, retest)
- Coverage (baseline validation, control adoption)
- Quality (false positive rate, rework rate, policy exceptions)
- Resilience (incident impact duration, recovery outcomes)
