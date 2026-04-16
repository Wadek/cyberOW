# CyberOW ↔ NIST AI Risk Management Framework (AI RMF 1.0) Mapping

**Document Purpose**  
This mapping demonstrates how the CyberOW One-Way Operating Way for AI-First Cybersecurity aligns with and satisfies the **NIST AI RMF 1.0** (January 2023). It shows that CyberOW is not only a cybersecurity operating model but also a **practical implementation** of trustworthy AI risk management principles.

The NIST AI RMF Core consists of four functions: **Govern**, **Map**, **Measure**, and **Manage**. CyberOW’s design principles (the Four One-Ways), phased delivery, Evidence Ledger, Mythos Core, and MILK scaffold provide strong, built-in coverage across all functions.

## 1. Govern – “A culture of risk management is cultivated and present”

CyberOW provides a strong foundation for organizational AI risk governance.

| NIST Govern Category / Outcome | CyberOW Alignment |
|--------------------------------|-------------------|
| Policies, procedures, and processes for AI risk management | OW Doctrine (One-Way Control, Evidence, Consolidation, Value Delivery) serves as the core policy set |
| Accountability structures and roles | Standardized Agent Roles (Observer, Analyst, Operator, Executor) with explicit decision rights and approval gates |
| Risk tolerance and culture | One-Way constraints and staged autonomy explicitly define risk tolerance and blast-radius limits |
| Oversight and continuous improvement | Monthly Steering, bi-weekly Architecture & Controls, weekly Use Case Review and Ops Feedback Loops |
| Integration with broader enterprise risk | Cyber Stacks (Govern, Identify, Protect, Detect, Respond, Recover) align cyber operations with enterprise risk posture |

**Strength**: Govern is cross-cutting in CyberOW — the OW principles infuse every phase and agent action.

## 2. Map – “Context is recognized and risks related to context are identified”

CyberOW excels at contextualizing AI agents in cybersecurity environments.

| NIST Map Category | CyberOW Alignment |
|-------------------|-------------------|
| Establish context and intended use | Work Decomposition into agentizable work units across six Cyber Stacks |
| Identify AI system capabilities, limitations, and potential impacts | Agent Roles table + Automation boundary (assist / prepare / execute) |
| Understand socio-technical environment and stakeholders | Explicit human approval gates and evidence-linked outputs |
| Categorize AI systems by risk | Classification of capabilities as Canonical / Complementary / Redundant / Bridge-only (OW-3) |
| Map dependencies and third-party risks | Security Reality Graph (Mythos Core) maps assets, identities, controls, exposures, and dependencies |

**Strength**: The Mythos Core Reality Graph provides a living, machine-readable map of the security environment.

## 3. Measure – “AI systems are evaluated for trustworthiness characteristics”

CyberOW’s Evidence Ledger and metrics framework directly support measurement.

| NIST Measure Category | CyberOW Alignment |
|-----------------------|-------------------|
| Assess validity, reliability, safety, security & resilience | OW-1 (One-Way Control) and OW-2 (Evidence Ledger) + immutable logging of all tool calls and outputs |
| Evaluate transparency, explainability, and accountability | Every agent output must produce an evidence ledger with source references, assumptions, and decision rationale |
| Measure fairness / bias (where applicable) and privacy | PII rules in Observer role + content rules for sensitive data at ingress |
| Track performance metrics over time | Defined metrics: cycle time, coverage, quality (false positive/rework rates), resilience (incident duration, recovery outcomes) |
| Use of independent testing / red teaming | Sandbox Autonomy phase + controlled digital twin simulations |

**Strength**: The immutable Evidence Ledger turns every AI action into auditable, measurable evidence — directly supporting NIST’s emphasis on accountability and transparency.

## 4. Manage – “AI risks are prioritized, allocated resources, and addressed”

CyberOW’s phased approach and guardrails make risk management actionable and iterative.

| NIST Manage Category | CyberOW Alignment |
|----------------------|-------------------|
| Prioritize risks and allocate resources | Phased Delivery (value realization mandatory at each phase boundary) + Steering forum |
| Implement controls and mitigations | One-Way Execution Scaffold (MILK), explicit approval gates, least-privilege agent identities |
| Monitor and respond to risks in real time | Full logging/monitoring of all agent tool calls + Ops Feedback Loop |
| Continuous improvement and adaptation | OW-3 Consolidation + redundancy classification + weekly refinement of work units and prompts |
| Incident response and recovery for AI-related events | Respond and Recover Cyber Stacks + post-incident learning synthesis into control backlog |

**Strength**: Staged autonomy (Read-Only → Operator → Supervised Execution → Sandbox) is a textbook example of risk-prioritized, incremental deployment.

## Overall Trustworthiness Characteristics Coverage (NIST Figure 4)

- **Valid & Reliable**: Evidence Ledger + metrics + retesting automation
- **Safe**: One-Way Control (Pull > Push) and blast-radius limitations
- **Secure & Resilient**: MILK scaffold, controlled environments, rollback plans
- **Accountable & Transparent**: Immutable evidence ledger for every output
- **Explainable & Interpretable**: Captured decision rationale and source references
- **Privacy-Enhanced**: PII rules, sensitive data content filtering at ingress, least privilege
- **Fair – Harmful Bias Managed**: Human review gates in Analyst/Operator roles + audit-ready evidence packs

## Conclusion & Recommendations

CyberOW provides **excellent native alignment** with NIST AI RMF 1.0, particularly in the areas of **accountability, transparency, safety, and staged risk management**. It goes beyond generic guidance by turning the RMF into executable Python-based components (Evidence Ledger, One-Way Scaffold, Agent decorators, etc.).

**Next Steps for Stronger Alignment**:
1. Add explicit NIST RMF references in governance policies.
2. Implement automated mapping of Evidence Ledger entries to specific RMF subcategories.
3. Create a CyberOW “Profile” document (per NIST guidance) tailored for defensive cybersecurity AI agents.
4. Include RMF mapping in every pilot use case review.

**References**  
- NIST AI RMF 1.0 (January 2023) — https://doi.org/10.6028/NIST.AI.100-1  
- NIST AI RMF Playbook (companion resource)

---

This file is now part of your documentation. You can extend it later with more detailed subcategory mappings if needed.

Would you like me to generate the next piece now? For example:
- `src/cyberow/core/evidence_ledger.py` (Pydantic-based immutable ledger)
- `docs/architecture.md` (full technical architecture)
- Or a simple `nist_rmf_playbook_integration.py` stub

Just tell me what to create next.
