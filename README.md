# ritvi-apps / legal — permanent redirect shim

> **Do not delete this repository. Do not disable Pages on it.**
> Doing either 404s a privacy-policy URL that two live Play listings point at,
> and that is grounds for an app to be removed from the store.

The documents themselves now live at
**<https://ritesh-firodiya.github.io/legal/>**.

Everything here is a redirect page. Each one keeps its original path, returns
200, carries `rel=canonical` to the new address, and renders a visible link so a
store reviewer with scripting disabled still reaches the document.

## Why it cannot be retired

These URLs are hardcoded inside app builds that are already installed on
people's phones. An install from last year asks for the old address and will
never be updated:

| App | Source |
|---|---|
| Charades | `src/app/settings.tsx:42` |
| Tic Tac Toe | `src/components/shared/ActionButtons.tsx:13` |
| Aakalan | `src/app/account.tsx:48` |
| AskCal | `apps/mobile/src/config/legal.ts:16`, `config/store.ts:33` |
| Chitragupt | `apps/website/src/components/marketing/SiteFooter.tsx:95` |

Both of the comments in `charades/settings.tsx` and `tic-tac-toe/ActionButtons.tsx`
record an earlier version of this exact mistake — a renamed repo and a Pages
site that was never enabled, both of which 404'd in production.

New app builds should point directly at `ritesh-firodiya.github.io/legal/...`.
The shims exist for the builds that cannot be changed.

## Map

| Old path | Now serves |
|---|---|
| `/legal/` | `/legal/` on the new site |
| `/legal/terms.html` | `/legal/terms.html` |
| `/legal/support/` | `/support/` |
| `/legal/<app>/<doc>.html` | the same path on the new site |

## Deploy

GitHub Pages, branch `main`, root. No build step.
