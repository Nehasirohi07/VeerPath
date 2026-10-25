# VeerPath AI — Project Index

> **Documentation only.** This file is the project notebook and progress tracker.
> It contains no application code, no executable examples, no secrets, no credentials, and no personal data.
> Entries are added only after the developer confirms them.

**Project:** VeerPath AI — AI-powered career transition platform for retired military veterans (initial focus: Indian Army veterans entering civilian employment)

**Working model:** all implementation code is written by hand and understood before it is committed. This document records only what has actually been written, run, and observed.

---

## 1. Project mission and product principles

**Mission:** Help veterans translate military experience into civilian competencies, identify appropriate career paths, discover suitable vacancies, prepare applications, and track employment outcomes.

**Defining product principle:**
> Respect the veteran's experience, preserve career dignity, and personalize the career path. Never automatically recommend junior roles simply because the candidate is transitioning from military to civilian employment.

**Derived rules the system must obey:**

| # | Principle | Consequence in the design |
|---|---|---|
| P1 | Rank and years of service must not determine civilian seniority | Seniority is derived from demonstrated responsibilities, not rank titles |
| P2 | Military rank is not equivalent to a civilian title | No rank-to-title mapping table; competency evidence is required instead |
| P3 | The veteran's stated career level is respected | Preferred level is an input, never silently overridden |
| P4 | Stretch opportunities are distinguished from proven strong fits | Confidence/evidence level is a first-class output of matching |
| P5 | Mandatory requirements cannot be outranked by similarity scores | Eligibility gates are evaluated before ranking, in the deterministic layer |
| P6 | Missing data is never treated as proof of suitability | Absent evidence reduces confidence and is surfaced as unknown |
| P7 | AI explanations are grounded in the real profile and vacancy | Explanation layer is constrained to retrieved evidence |
| P8 | No invented vacancies, no unverified employer claims | Data provenance and freshness are recorded with every listing |
| P9 | Uncertain assessments are visible to the veteran | Unknown/unverified markers are shown, not hidden |

---

## 2. Current architecture

**Status: nothing implemented.** The workspace is empty (verified). The architecture below is the *target*, to be built gradually and only when the current stage justifies it.

**Target stack and responsibility split:**

- **Go backend** — HTTP APIs, authentication and authorization, veteran profiles, experience records, job and employer records, career preferences, matching rules and final ranking, application tracking, audit events, data access and validation.
- **Python AI service (FastAPI)** — skill extraction, military-to-civilian competency mapping, semantic search, résumé analysis, career-path suggestions, evidence-grounded explanation generation. **Must not override mandatory eligibility rules or the veteran's stated preferences.**
- **PostgreSQL** — structured application data. `pgvector` introduced only after relational design and the initial matching implementation are understood.
- **Frontend (React/Next.js)** — introduced only after backend and data model are understandable.
- **Infrastructure (Docker, CI/CD, caching, background jobs, observability)** — introduced only when the core application justifies it. No premature microservices.

**Deliberate architectural constraint:** the deterministic matching and eligibility rules live in Go (explicit, testable, auditable). AI is an *assistive* layer that extracts, maps and explains — it never decides eligibility or final ranking on its own.

---

## 3. Repository and file inventory

**Workspace:** `D:\projects\veerpath` (Windows host, commands run through Git Bash)
**Git repository:** not initialized at first inspection
**Last inventory check:** initial setup (empty workspace)

| Path | Purpose | Status |
|---|---|---|
| `docs/VEERPATH_PROJECT_INDEX.md` | Project notebook and progress tracker (this file) | Created during project setup, documentation only |

Everything else: **not created**.

**Planned top-level layout (to be created manually by the developer, step by step):**

| Path | Purpose | Status |
|---|---|---|
| `go.mod` | Go module definition for the backend | Planned |
| `cmd/` | Executable entry points (main packages) | Planned |
| `internal/` | Backend packages not importable by other modules | Planned |
| `migrations/` | Hand-written SQL schema migrations | Planned |
| `pkg/` or `internal/` subpackages | Shared domain types (decision pending) | Planned |
| `ai-service/` | Python FastAPI service | Planned |
| `web/` | React/Next.js frontend | Planned (far future) |
| `docs/` | Index plus future design notes | Exists (index only) |
| `README.md` | Project overview | Planned |
| `.gitignore` | Ignore rules | Planned |

---

## 4. Learning roadmap

**Developer profile (self-reported at intake):**

| Area | Level | Notes |
|---|---|---|
| Go | Comfortable with basics | Structs, slices, maps, errors, interfaces |
| Python | None | Real gap; protected in the plan |
| SQL | Has written SQL | SELECT/INSERT/JOIN |
| Schema design | Has designed tables | Keys and constraints |
| REST APIs | Has built one before | Endpoints, status codes, bodies |
| Testing | Not yet confirmed | To be verified when we reach tests |
| Git / Docker / deployment | Not yet confirmed | To be verified |

> All levels above are **self-reported** and are recorded as claims, not verified skills. Each is validated when we first exercise it.

**Planned phases (adjusted to the profile above):**

| Phase | Focus | Adjustment for this developer |
|---|---|---|
| 0 | Skills assessment, roadmap, project index | ✅ Complete |
| 1 | Product, requirements, architecture, repository structure | Normal |
| 2 | Go fundamentals needed for this project | **Compressed** — taught through VeerPath's own domain types, not toy examples |
| 3 | Basic Go HTTP server written by hand | Normal |
| 4 | API design, validation, error handling, testing | **Compressed** on API basics; test discipline still taught in full |
| 5 | PostgreSQL and relational data modelling | **Compressed** on SQL syntax; depth on constraints, transactions, migrations, query safety |
| 6 | Veteran profiles and experience records | Normal — first real domain modelling |
| 7 | Python fundamentals and FastAPI | **Protected, not compressed** — highest-risk phase |
| 8 | AI service built manually | Normal |
| 9 | Competency extraction and military→civilian mapping | Normal |
| 10 | Seniority-aware matching engine | Normal — heart of the product |
| 11 | Semantic search and AI-generated explanations | Normal (`pgvector` here or later) |
| 12 | Real job data, compensation, application tracking | Normal |
| 13 | Frontend built manually | Normal |
| 14 | Auth hardening, privacy, authorization, auditability | Interleaved, not deferred |
| 15 | Full-system testing and a consented pilot | Normal |

---

## 5. Current phase and current task

**Current phase:** Phase 1 — product, requirements, architecture, repository structure. (Toolchain setup runs alongside it, since the machine has no Go, Python, PostgreSQL, Docker or Node installed.)

**Current task:** **Task 1 — Toolchain and environment setup.**
Install and verify the Go toolchain and editor. No project code is written in this task.

**Explicitly deferred installations:** PostgreSQL (Phase 5), Python (Phase 7), Docker and Node (Phase 13/14).

---

## 6. Concepts learned

*Recorded only after the developer demonstrates understanding. Nothing is recorded here yet.*

| Concept | Demonstrated how | Date | Status |
|---|---|---|---|
| — | — | — | — |

**Concepts explained but not yet demonstrated:** none.

---

## 7. Concepts needing revision

| Concept | Observation | Planned remedy |
|---|---|---|
| — | — | — |

---

## 8. File-by-file implementation status

**Status vocabulary:** Planned → In progress → Written by developer → Reviewed → Tested → Verified complete.

| File path | Purpose | Status | Concepts it teaches | Dependencies | Review | Tests |
|---|---|---|---|---|---|---|
| _(none yet)_ | — | — | — | — | — | — |

**Rule:** a file moves to *Verified complete* only when it was written by hand, reviewed against the requirements, and a check actually ran with credible output.

---

## 9. Verified features

*None. Nothing has been implemented yet.*

---

## 10. Tests and their actual results

| Date | Check | Command / method | Result | Notes |
|---|---|---|---|---|
| — | — | — | — | — |

**Rule:** no test is recorded as passing without running it and observing the output.

---

## 11. Known bugs and technical debt

| Item | Severity | Notes |
|---|---|---|
| Go, Python, PostgreSQL, Docker, Node not installed on this machine | Blocking setup | Toolchain setup is Task 1 |
| Git repository not initialized | Not a bug | To be done manually by the developer |
| Windows execution aliases intercept `python` / `python3` | Environment gotcha | Remembered for Phase 7; install Python properly and check PATH |

---

## 12. Architecture decisions and reasons

| # | Decision | Reason | Status |
|---|---|---|---|
| AD-1 | Go for the deterministic core (eligibility, matching, ranking) | Explicit, testable, auditable rules; AI must not overrule eligibility | Proposed |
| AD-2 | Python + FastAPI as a separate assistive service | Best ecosystem for NLP/LLM work; keeps AI failure from breaking core APIs | Proposed |
| AD-3 | HTTP framework: Gin **or** Chi — one only, chosen with trade-offs explained | Avoid framework churn; teach the reasoning, then commit | **Open — decision pending, Phase 3** |
| AD-4 | PostgreSQL as the single relational store | Strong constraints and transactional integrity for user/vacancy data | Proposed |
| AD-5 | `pgvector` deferred until relational design and rule-based matching are understood | Prevent vector search from hiding a weak data model | Proposed |
| AD-6 | Frontend and infrastructure deferred | Avoid premature complexity; no unnecessary microservices | Proposed |

---

## 13. API and database design status

**API:** not started. Open questions to resolve in Phase 4: resource naming, versioning strategy, error response shape, pagination approach, authentication scheme.

**Database:** not started. Open questions to resolve in Phase 5: identifier strategy, how experience records attach to profiles, how competency evidence is stored, how vacancy provenance and freshness are represented, how preferences are versioned.

**Non-negotiable design inputs:** the nine product principles in section 1, especially P2 (no rank-to-title equivalence), P5 (eligibility before ranking) and P6 (missing data ≠ suitability).

---

## 14. Security and privacy checklist

*Nothing implemented. Tracked so it is designed in, not bolted on.*

- [ ] Password hashing and secure authentication
- [ ] Authorization and ownership checks on every private resource
- [ ] Input validation at the API boundary
- [ ] SQL injection prevention (parameterised queries only)
- [ ] Secret management (no secrets in repository or chat)
- [ ] Encryption and handling of sensitive data at rest and in transit
- [ ] Secure file uploads (résumés)
- [ ] Logging that never exposes personal information
- [ ] Consent and employer data-sharing permissions
- [ ] Account deletion and data export
- [ ] Rate limiting
- [ ] Audit trails for sensitive actions
- [ ] Safe handling of LLM inputs and outputs (prompt injection, data leakage)

**Standing privacy rules for this project:**
1. Never collect classified or operationally sensitive military information.
2. Collect only what the service needs.
3. Never request or store real passwords, API keys, or private service records in this conversation.

---

## 15. Next three recommended tasks

1. **Task 1 — Toolchain setup:** install and verify Go and an editor; confirm `go version` and `go env`. (Concepts understood before implementation.)
2. **Task 2 — Repository foundation:** developer initialises Git, writes `.gitignore` and `README.md`, and creates the Go module by hand; understand what each artifact is for.
3. **Task 3 — First hand-written Go program:** a minimal health/status executable in the `cmd/` layout, with an explanation of `package main`, `func main`, and how build/run differ.

---

## 16. Work log and lessons learned

**Log 1 — initial setup**

- Workspace started empty at `D:\projects\veerpath`: no source, no docs, no Git repository.
- Only Git was present (`git 2.55.0.windows.5`); `go`, `python`, `pip`, `psql`, `docker` and `node` were absent.
- `python --version` produced the Windows execution-alias message rather than a version, confirming no real Python install.
- Self-assessment recorded as self-reported (section 4).
- Developer authorized creation of this index file (documentation only). No other file was written.
- Roadmap adjusted: Phases 2, 4 and 5 compressed; Phase 7 (Python) explicitly protected.
- **Lesson:** the project has no code by design. Progress is measured in demonstrated understanding, not in files generated.
