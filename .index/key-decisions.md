# Key Decisions

## ADR-001 — Static HTML as delivery vehicle
- **Decision:** Ship the Intern US strategic analysis as a self-contained HTML page.
- **Rationale:** Zero deps, easy embed in Element/SDK hosts and static hosting.
- **Consequence:** No server logic, limited interactivity, content edits require HTML surgery.

## ADR-002 — External NotebookLM for “AI”
- **Decision:** Link out to Google NotebookLM rather than embed an LLM.
- **Rationale:** Fast path to document Q&A without backend cost.
- **Consequence:** Requires Google auth; not white-labeled; not POPIA-controlled by this repo.

## ADR-003 — Neon visual revamp on green content styles
- **Decision:** Global neon theme applied via CSS while many content boxes retain olive/green inline colors.
- **Rationale:** Apparent iterative redesign (`Revamp styles with neon color scheme` commit).
- **Consequence:** Visual inconsistency; dual palettes maintainability debt.

## ADR-004 — Analysis artifacts committed to repo (2026-07-24)
- **Decision:** Persist comprehensive analysis + `.index/` in git for team/agent continuity.
- **Rationale:** User requested planning-grade deliverable; memory protocols require durable state.
