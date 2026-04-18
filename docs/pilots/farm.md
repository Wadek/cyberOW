# Pilot: Farm Network

**Repo:** github.com/Wadek/Farm  
**Type:** Hyperlocal farming and marketplace platform  
**Stack:** Python, FastAPI, SQLAlchemy, SQLite, Claude Code CLI  
**Started:** 2026-04-18  
**Status:** Active development

---

## What it is

A hyperlocal food network platform for a community of ~5000 families within a 20km radius.
Gamified to encourage participation from hobby gardeners (single grow box) to small farms (5 hectares).
Delivery modelled as a node network — walkable, rideable by horse or ATV.

Core entities: User, Node (growing location), Produce, Listing, Transaction (MYC token ledger), Message.

---

## CyberOW principles applied

### OW-2: Evidence ledger
- `Transaction` table is append-only — no update or delete routes
- `JournalSession` + `JournalEntry` tables record every Claude CLI tip request:
  context snapshot, question, response, status

### OW-1: Pull over Push
- Daily tip generation is user-triggered (`POST /tips/daily`)
- Claude CLI is called per-question with isolated subprocess — no shared context between calls
- Background task fires questions but does not mutate any state beyond the journal ledger

### Security defaults applied
- `.env` gitignored, `.env.example` committed
- Git identity: `Wadek@users.noreply.github.com`
- No personal data in committed files
- Passwords hashed with bcrypt, never stored plain

### Agent role classification
- The Claude CLI tip runner is an **Observer** role:
  read-only context input, text output only, no state changes beyond the journal ledger

---

## What is not yet built

- MYC token engine (HyphaeLogic port from mycelium project)
- Auth routes (JWT or similar)
- Node, Produce, Listing, Transaction API routes
- Neighbourhood-level aggregation
- Frontend (deferred — Python API first)

---

## Lessons for CyberOW test suite

- Append-only enforcement needs a route-level check, not just a model-level one —
  SQLAlchemy won't stop a DELETE route from being added later
- Claude CLI subprocess isolation works cleanly as an Observer pattern;
  document this as a reference implementation in MILK
- Weather context from Open-Meteo (no API key) is a good pattern for
  grounding AI queries in real-world state without external dependencies
