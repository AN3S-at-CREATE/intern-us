# Dead / Unused Code Log

| Item | Evidence | Risk | Recommended action |
|------|----------|------|--------------------|
| Tailwind CDN script | `cdn.tailwindcss.com` loaded; **0** Tailwind utility class tokens in markup | Medium (extra network, supply-chain) | Remove script unless utilities will be adopted |
| Cloudflare challenge leftover | Trailing IIFE referencing `/cdn-cgi/challenge-platform/...` | Medium (404 noise, odd iframe) | Delete leftover script |
| `.github/workflows/index.html` | MD5 identical to root `indec.html`; not a workflow | High (confuses CI/reviewers; bloat) | Move to root as `index.html` or delete after sync strategy |
| `modal.onremove` handler | Not a standard DOM event; overflow never restored | High (UX scroll lock) | Restore overflow inside `closeModal`; stopPropagation on × |
| Element/Data SDK scripts locally | Always 404 off host platform | Low (documented graceful degrade) | Keep guarded init; document host requirement |
| Unused Tailwind + unused SDK config surface for most readers | Edit panel only on Element host | Low | Document; or strip SDK if Pages-only |
