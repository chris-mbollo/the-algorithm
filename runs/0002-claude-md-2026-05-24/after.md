# Claude Code Instructions

## About this repo
`/Users/macbookpro` is a git meta-repo at $HOME — **don't commit here.** Each project below has its own repo; do git work inside the project folder. When working in a project, read its `CLAUDE.md` and `SPEC.md` first.

## Profile — Chris Mbollo (GitHub: chris-mbollo)
**Priorities:** Speed first, quality second. Not optimizing for cost. Building in public.

**Communication style:** Direct answers. Make the call — don't list five options when one is right. I think in frameworks, not lists. Correct me fast — don't validate slowly. No fluff, no hedging.

## Skills
Routing: business decisions → `ceo-advisor`. GTM/sales → `distribution-strategy`. UI → `frontend-design`. Don't fetch well-known sites just to summarize — fetch only for current/specific data.

## Design References
- **21st.dev** (https://21st.dev/components) — check for ready-made components before building from scratch.
- **`magic` MCP** — programmatic access to 21st.dev components.

## Projects
- **DealHawk** `deal-hawk/` — SFR deal finder. Vanilla JS + Vercel + Haiku + RapidAPI. https://deal-hawk-two.vercel.app · edit `public/index.html` directly.
- **TrackRecord** `trackrecord/` — sales pipeline tracker. Vanilla JS + Supabase + Vercel. https://trackrecord-chi.vercel.app
- **chris-mbollo-site** `chris-mbollo-site/` — personal brand site. www.chrismbollo.com · Beehiiv + /audit Cal.com funnel.
- **SmartCart** `smartcart/` — grocery price optimizer. Expo + Supabase + SerpAPI.
- **BuyerBase** `land-buyer-finder/` — land buyer intel. ATTOM API, zip search.
- **Owed** `Owed/` + `owed-api/` — iOS OON therapy reimbursements. Expo+TS+NativeWind+RevenueCat.
- **Vanguard Sales AI** — sales AI Electron overlay. Deepgram + Claude.
- **ADHD Companion** `adhd-app/` — Expo + Supabase + Claude.
- **Brand Gap Agent** `brand-gap-agent/` (real root: `brand-gap-vercel/`).
- **Poster Agent** — autonomous X/Reddit poster, reads Brand Gap data.

## New Project Checklist
Before first deploy:
1. **SPEC.md + local CLAUDE.md** — scaffold from `~/.claude/templates/`. SPEC = what the system does. CLAUDE.md = how to work in the repo. If `.code-review-graph/` exists, append `~/.claude/templates/code-review-graph.md`.
2. **Security audit** — review all API endpoints for: unbounded proxy (no model allowlist, no max_tokens cap), XSS via `innerHTML` with unescaped data, prompt injection (user input concatenated into AI prompts), path traversal in proxy endpoints, CORS wildcard on endpoints hitting paid APIs. Fix CRITICAL/HIGH before deploying.
3. **Auto research** (web apps with `public/`) — scaffold from `~/.claude/templates/auto-research.md`.

## Lab Notes
- **Over-engineering before scoping:** Default to smallest working version. Ask scope before building.
- **Spinning before understanding:** Understand the problem fully before starting — ask one clarifying question if needed.
- **Measure before proposing:** Run the real audit first — Lighthouse, chrome-devtools, grep, curl. Never propose fixes from intuition. If data shows the system is fine, say so.
