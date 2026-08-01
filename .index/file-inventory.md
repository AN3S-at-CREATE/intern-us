# File Inventory

| Path | Purpose | Status |
|------|---------|--------|
| `indec.html` | Primary static report page (content, CSS, JS modal, Element SDK config bridge) | Active |
| `AGENTS.md` | Cursor Cloud agent runbook (serve/test notes) | Active |
| `.github/workflows/jekyll-gh-pages.yml` | Deploy to GitHub Pages via Jekyll | Active |
| `.github/workflows/jekyll-docker.yml` | CI Jekyll build in Docker on push/PR | Active |
| `.github/workflows/index.html` | Byte-identical copy of `indec.html` (misplaced) | Deprecated / misplaced |
| `COMPREHENSIVE_REPO_ANALYSIS.md` | Full repository analysis & super-app roadmap; uses checkout-relative commands, reproducible evidence descriptions, and tagged code fences | Active (analysis artifact) |
| `REPO_ANALYSIS_MEMORY.md` | Persistent analysis state for agents | Active |
| `.index/*` | Agent/human project context index, including review-corrected architecture, decision terminology, and markdown formatting | Active |
| `.agent/` | Reserved agent state directory | Active |

## Explicitly absent (expected for this repo type, but gaps for maturity)
- No `README.md`, `LICENSE`, `.gitignore`
- No `package.json` / `requirements.txt` / `Gemfile` / `_config.yml`
- No root `index.html` (typo filename `indec.html` blocks default directory index)
- No `tests/`, no backend, no DB, no Docker app compose
