# Dead / Unused Code Log

| Item | Evidence | Risk | Recommended action |
|------|----------|------|--------------------|
| Tailwind CDN utility layer | `cdn.tailwindcss.com` loaded with **0** utility class tokens; Preflight still provides global reset styles | Medium (extra network, supply-chain; unsafe removal can alter rendering) | Identify and preserve required reset styles, visually verify parity, then remove the CDN |
| Cloudflare challenge leftover | Trailing IIFE referencing `/cdn-cgi/challenge-platform/...` | Medium (404 noise, odd iframe) | Delete leftover script |
| `.github/workflows/index.html` | MD5 identical to root `indec.html`; not a workflow | High (confuses CI/reviewers; bloat) | Move to root as `index.html` or delete after sync strategy |
| `modal.onremove` handler | Not a standard DOM event; overflow never restored | High (UX scroll lock) | Restore overflow inside `closeModal`; stopPropagation on × |
| Element/Data SDK scripts locally | Always 404 off host platform | Low (documented graceful degrade) | Keep guarded init; document host requirement |
| Unused Tailwind utilities + unused SDK config surface for most readers | Preflight remains active; edit panel only on Element host | Low | Document; audit Preflight before CDN removal; strip SDK only if Pages-only |
