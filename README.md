# ritvi-apps / legal

Published privacy policies for Ritvi Apps, served by GitHub Pages at
**https://ritvi-apps.github.io/legal/**

This repository is public on purpose and for one reason: Google Play and the App
Store require a privacy policy at a URL they can fetch, and Pages cannot serve a
private repository on the free plan. The app repositories stay private.

| App | Package | Policy |
|---|---|---|
| Aakalan — Split Expenses | `com.riteshf.aakalan` | [/aakalan/privacy-policy.html](https://ritvi-apps.github.io/legal/aakalan/privacy-policy.html) |
| Charades - Act it Out! | `com.riteshf.charadesbollywood` | [/charades/privacy-policy.html](https://ritvi-apps.github.io/legal/charades/privacy-policy.html) |

## Editing

Each policy is a single self-contained HTML file — no build step, no
dependencies. Push to `main` and Pages redeploys.

The source of truth for a policy is the copy in that app's own repository
(`.context/documents/research/privacy-policy.html`). Change it there, then copy
it here, so the app and the published page cannot disagree.

**A store listing URL is not something to break casually.** Play checks that the
URL resolves, and an app whose policy 404s can be taken down. Do not rename this
repository or move these paths without updating both store listings and the
in-app links that point at them.
