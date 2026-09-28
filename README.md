# emvori-status

Stable public entry for Emvori.

Live page: https://mastatrill.github.io/emvori-status/

This repository is a continuity and trust surface only:

- health-checked Open button (JSON ready on a non-tunnel public origin)
- public plan limits
- privacy and model routing disclosure
- trust center
- public briefs
- support contact
- public gates / scoreboard

It is not an Aetheron token surface and must not advertise `emvori.ai` until registry ownership and DNS are verified.

## Pages

- `index.html` — public entry
- `trust.html` — what is stored, what leaves, what requires approval
- `briefs.html` — index of public briefs
- `briefs/` — dated HTML briefs
- `brand.html` — public voice rules
- `plans.html` / `privacy.html` / `models.html` / `scoreboard.html` / `support.html`

## current.json contract

- `primary` / `fallback` — stranger-reachable paid origins only. Tailscale, Cloudflare quick tunnels, ngrok, and nip.io are not production.
- `ready` — set `true` only after a phone-on-cellular probe of `/api/emvori-health` or `/railway-health` returns JSON `{ ready: true }` on `primary`.
- `operatorOrigin` / `operatorTailscale` — operator reachability only. The status page may link them as “not public-live.”
- `legacyOrigin` — AppDeploy warmup / paused shell. Never an Open target.
- `reason` — shown when `ready` is false.

`npm run health:public` in `MastaTrill/Emvori` fails if primary/fallback are tunnels or if `ready` is false.
