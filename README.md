# VeerPath AI 

AI-powered career transition platform for Indian Army veterans moving into civilian employment.

## The problem 

Military experience does not translate clearly into civilian hiring language.
Veterans are routinely offered junior roles because rank and years of service are read as the only signal, while demonstrated responsibilities, leadership scope and qualifications are ignored.

## Core principle 

Military rank and years of service never determine civilian seniority on their
own. Seniority is assessed from demonstrated responsibilities, achievements,
qualifications and stated preference. The platform explains whether a role is a
strong fit, a stretch opportunity, or an alternative pathway — and never
silently downgrades a candidate.


## Planned architecture 

- **Go** -- modular monolith: HTTP APIs, authentication, authorisation, hard eligibility rules, final ranking, audit events.
- **Python + FastAPI** -- AI service: experience analysis, competency mapping, semantic search , grounded explanation. advisory only; it cannot override backend rules or a veteran's stated preferences.
- **PostgreSQL** -- structured application data. Semantic search  via pgvector only after the relational model is solid.
- **React / Next.js** -- frontend, introduced after the backend and data model.

## Status 

Phase 1 -- toolchain setup and repository foundation. **Pre-alpha: no features implemented yet.** Verified progress is tracked in 
`docs/VEERPATH_PROJECT_INDEX.md`.

## Documentation

- `docs/VEERPATH_PROJECT_INDEX.md` -- architecture, decisions , learning log and verified progress. The single source of truth for project state.