# CyberOW Test Suite – Specification

**Status:** Staged — not yet implemented  
**Purpose:** A runnable suite that any Claude session can invoke against a project to verify CyberOW compliance.  
**Design principle:** The suite is an Observer-role agent — read-only, no state changes, evidence-linked output.

---

## What it checks

### 1. Security defaults
- [ ] `.env` is gitignored
- [ ] No secrets, emails, or personal identifiers found in committed files
- [ ] Git history contains no personal email addresses (scan author fields)
- [ ] No hardcoded credentials in source files (pattern scan)
- [ ] `.env.example` exists with placeholder values

### 2. OW-1 compliance — Pull over Push
- [ ] No background job or scheduler initiates destructive actions without an explicit trigger
- [ ] Any automation that changes state requires an identifiable caller/approver

### 3. OW-2 compliance — Evidence ledger
- [ ] At least one append-only ledger table exists for any feature that produces consequential outputs
- [ ] Ledger tables have no `UPDATE` or `DELETE` routes exposed
- [ ] AI-generated outputs (if any) are stored with: input, model/source, output, timestamp, status

### 4. OW-3 compliance — No redundant capabilities
- [ ] No duplicate implementations of the same logical service
- [ ] Dependencies in requirements/pyproject are justified (no unused packages)

### 5. OW-4 compliance — Value at phase boundaries
- [ ] Each implemented phase has at least one measurable endpoint or metric
- [ ] No dead code paths that were started but never completed

### 6. Code quality gates
- [ ] All tests pass
- [ ] No test uses a live external service without a mock fallback
- [ ] Test coverage exists for every model and every route
- [ ] No commented-out code blocks

### 7. NIST AI RMF alignment (for AI-assisted features)
- [ ] AI role is classified (Observer / Analyst / Operator / Executor)
- [ ] Human approval gate exists for any Operator or Executor action
- [ ] PII handling is documented or not applicable

---

## Output format

The suite produces a structured report:

```
CyberOW Compliance Report
Project: <name>
Date: <iso-date>
Runner: Claude Code (Observer role)

PASS  security.env_gitignored
PASS  security.no_hardcoded_secrets
FAIL  ow2.ledger_no_delete_routes  — listings route exposes DELETE /listings/{id}
WARN  ow4.phase_metrics            — no metrics endpoint found for Phase 1
...

Score: 11/13 checks passed
```

---

## Implementation plan (future)

- `src/cyberow/guards/compliance_runner.py` — orchestrates checks
- `src/cyberow/guards/checks/` — one module per check category
- `src/cyberow/evidence-ledger/report_writer.py` — writes append-only compliance run record
- CLI: `cyberow check --project /path/to/project`
- FastAPI route (optional): `POST /cyberow/check` for integration into CI pipelines

---

## Pilot results

| Project | Date | Score | Notes |
|---------|------|-------|-------|
| Farm (github.com/Wadek/Farm) | 2026-04-18 | Manual review — suite not yet built | See `docs/pilots/farm.md` |
