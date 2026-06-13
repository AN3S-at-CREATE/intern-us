# AGENTS.md

## Cursor Cloud specific instructions

### What this repo is
A single, self-contained **static HTML** business/investment report (no backend, no
database, no build step). The primary page is `indec.html` at the repo root (note the
spelling — it is `indec.html`, not `index.html`). `.github/workflows/index.html` is a
duplicate copy of the same page. CI (`.github/workflows/*.yml`) builds/deploys the site
to GitHub Pages via Jekyll; that pipeline is for deploy only and is not needed for local
development.

### Dependencies
There are **no dependencies, package manager, or lockfiles** — nothing to install. The
update script is intentionally a no-op runtime check. `python3` (3.12) and `node` (22)
are preinstalled.

### Run it (dev)
Serve the directory with any static HTTP server and open the page by name:

```bash
python3 -m http.server 8000   # then open http://localhost:8000/indec.html
```

Caveat: because the file is named `indec.html` (not `index.html`), the directory index
(`http://localhost:8000/`) does **not** render the report — request `/indec.html`
explicitly.

### Lint / test / build
There is no lint, test, or build tooling configured in the repo. "Testing" means serving
the HTML and opening it in a browser. The core interactive feature is the **Strategic
Mind Map** image near the bottom: clicking it triggers `openImageModal()` to show a
full-size overlay with an `×` close button.

### Non-obvious notes
- The page references external resources that require internet access to fully render:
  the Tailwind CDN (`cdn.tailwindcss.com`) and the mind-map image on `iili.io`. The page
  still loads and the modal still works without them; the image just falls back to a
  placeholder.
- `<script src="/_sdk/element_sdk.js">` and `data_sdk.js` are provided by an external
  hosting platform and are **not** in this repo. They 404 locally with no ill effect —
  the page renders from its hardcoded `defaultConfig`.
