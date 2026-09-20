# ritvi-apps / legal

Published privacy policies for Ritvi Apps, served by GitHub Pages at
**https://ritvi-apps.github.io/legal/**

This repository is public on purpose and for one reason: Google Play and the App
Store require a privacy policy at a URL they can fetch, and Pages cannot serve a
private repository on the free plan. The app repositories stay private.

| App | Package | Policy |
|---|---|---|
| AskCal: AI Calorie Counter | `com.riteshf.askcal` | [privacy](https://ritvi-apps.github.io/legal/askcal/privacy-policy.html) · [delete data](https://ritvi-apps.github.io/legal/askcal/delete-account.html) · [get](https://ritvi-apps.github.io/legal/askcal/get.html) |
| Aakalan — Split Expenses | `com.riteshf.aakalan` | [privacy](https://ritvi-apps.github.io/legal/aakalan/privacy-policy.html) · [delete account](https://ritvi-apps.github.io/legal/aakalan/delete-account.html) |
| Chitragupt | `com.chitragupt.app` | [privacy](https://chitragupt.ai/legal/privacy) · [delete account](https://ritvi-apps.github.io/legal/chitragupt/delete-account.html) |
| Charades - Act it Out! | `com.riteshf.charadesbollywood` | [privacy](https://ritvi-apps.github.io/legal/charades/privacy-policy.html) |
| Tic Tac Toe | `com.riteshf.tictactoe` | [privacy](https://ritvi-apps.github.io/legal/tictactoe/privacy-policy.html) |

Chitragupt is the one exception to "everything is served from here": it has its
own website, so its privacy policy stays at `chitragupt.ai/legal/privacy` where
it is a real page of the product rather than a copy. Only the account-deletion
page lives here, because Play wants a URL a reviewer can open **without signing
in**, and every deletion surface inside the product sits behind auth.

Every other app is served from here, so there is one copy of each document and
one place to fix a mistake. That is the whole reason this repo exists: all three
apps previously published — or failed to publish — their policy somewhere
different, and two of the three links were dead.

> **Retire the old Charades URL.** `charades-bollywood.vercel.app/privacy-policy`
> still resolves and still carries the old, wrong contact address. It has no
> source in any repository, so it cannot be corrected — take the Vercel project
> down or redirect it here, or it will keep serving a stale legal document.

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

## `askcal/get.html`

The link AskCal puts on a shared post. AskCal is two store listings — Play
froze `com.riteshf.askcal` at first publish and iOS is its own bundle — so
whichever one went on the post would be wrong for half the people who saw it.
This page reads the visitor's device and forwards to the right store.

Both store links are in the markup and visible without JavaScript: a crawler
building a link preview, a browser with scripting off, and any desktop visitor
all get a working page rather than a blank redirect. Desktop is left to choose
rather than guessed at — a machine that can install neither is not helped by
being sent to one.
