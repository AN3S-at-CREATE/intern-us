# Architecture

## System type
Single-page **static document** with light client-side interactivity. Not a multi-service application.

```text
Browser
  ├─ indec.html (content + ~750 lines custom CSS + inline JS)
  ├─ External: cdn.tailwindcss.com (loaded, unused by classes)
  ├─ External: iili.io mind-map PNG
  ├─ External: notebooklm.google.com (AI chat deep-link)
  ├─ Optional host: /_sdk/element_sdk.js + data_sdk.js (404 locally)
  └─ Leftover: Cloudflare challenge iframe script (404 locally)
```

## Runtime
- Dev: `python3 -m http.server 8000` → open `/indec.html`
- Deploy: GitHub Actions Jekyll → GitHub Pages (root source `./`)

## Interactive surfaces
1. **Mind-map modal** — `openImageModal(src)` creates fixed overlay; close via × or backdrop.
2. **Config theming** — `defaultConfig` + `onConfigChange` when `window.elementSdk` present.
3. **AI assistant CTA** — navigates to external NotebookLM notebook (new tab).

## Data
All content is hardcoded in HTML. No API, auth, persistence, or PII collection in-repo.
