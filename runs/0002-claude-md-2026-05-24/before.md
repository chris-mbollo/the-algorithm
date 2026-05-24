# Claude Code Instructions

## About this repo
`/Users/macbookpro` is a git meta-repo at the home directory — no commits, everything untracked. **Do not commit here.** Each project below has its own repo; do all git work inside the project folder. When working inside a project, read that project's `CLAUDE.md` and `SPEC.md` first. There is no shared build/lint/test at this level — every project has its own stack.

## Profile
Chris Mbollo (GitHub: chris-mbollo). Builder, content creator, and sales professional. 3 years as an appointment setter and high ticket closer — deep proficiency in sales psychology, objection handling, and closing. Currently setting at Data Engineering Academy to fund the building. Ships SaaS products and micro-apps for the creator economy using Claude Code. Documents the building process publicly on YouTube, X, and Instagram. Runs a newsletter and website around the "Content vs. Capital" framework — helping creators understand platform-dependent income vs. ownable assets.

**Priorities:** Speed first, quality second. Not optimizing for cost. Building in public — what ships reflects directly on me.

**Communication style:** Direct answers. Make the call — don't give five options when one is clearly right. I think in frameworks, not lists. If something is wrong, say it. I'd rather be corrected fast than validated slowly. No fluff, no hedging.

## Skills
- Strategic / business decisions → invoke `ceo-advisor` before answering
- Selling / GTM / customer acquisition → invoke `distribution-strategy` before answering
- UI work → invoke `frontend-design`
- Don't fetch well-known sites just to summarize — fetch only for current/specific data

## Design References (Website/UI)
- **Godly** (https://godly.website) — curated gallery of top-tier web design. User must provide a screenshot of the chosen reference — visual input is critical.
- **21st.dev** (https://21st.dev/components) — React component marketplace. Check here for ready-made components before building from scratch.
- **`magic` MCP (21st.dev)** — programmatic access to 21st.dev components.

## Projects
- **DealHawk** — wholesale SFR deal finder. `deal-hawk/` · https://deal-hawk-two.vercel.app · vanilla HTML/CSS/JS, Vercel serverless, Anthropic (Haiku), RapidAPI. No build step — edit `public/index.html` directly.
- **TrackRecord** — rep-owned sales pipeline tracker. `trackrecord/` · https://trackrecord-chi.vercel.app · vanilla JS + Supabase + Vercel. V1 shipped 2026-05-06.
- **chris-mbollo-site** — personal brand site. `chris-mbollo-site/` · www.chrismbollo.com. Beehiiv newsletter + /audit funnel with Cal.com.
- **SmartCart** — grocery price optimizer. `smartcart/` · Expo + Supabase + SerpAPI.
- **BuyerBase** — land buyer intelligence app. `land-buyer-finder/` · ATTOM API, zip search.
- **Owed** — iOS app for OON therapy reimbursements. `Owed/` (Expo+TS+NativeWind+RevenueCat) + `owed-api/` backend. Pre-code, 8-week V1 roadmap (2026-05-07).
- **Vanguard Sales AI** — sales AI Electron overlay. Deepgram + Claude. DEA first client.
- **ADHD Companion** — `adhd-app/` · Expo + Supabase + Claude.
- **Brand Gap Agent** — brand analysis tool. `brand-gap-agent/` (real root is `brand-gap-vercel/` subdir).
- **Poster Agent** — autonomous X/Reddit poster, reads Brand Gap data (JS, public).

## New Project Checklist
Every new project gets these four things set up before the first deploy:

1. **SPEC.md** — create at project root using `~/.claude/templates/SPEC.md`. Define goal, core flows, contracts, out-of-scope, "done when" before writing code. SPEC = what the system does. CLAUDE.md = how to work in the repo.

2. **Local CLAUDE.md** — at project root. Include: stack, architecture, key file paths, business logic rules, what not to touch. If `.code-review-graph/` exists, append `~/.claude/templates/code-review-graph.md` to the end of the file.

3. **Security audit** — before going live, review all API endpoints for: unbounded proxy (no model allowlist, no max_tokens cap), XSS via `innerHTML` with unescaped data, prompt injection (user input concatenated into AI prompts), path traversal in proxy endpoints, CORS wildcard on endpoints hitting paid APIs. Fix CRITICAL and HIGH findings before deploying.

4. **Auto research** (web apps with a `public/` folder) — copy the research loop from DealHawk: `research/research.js` (Karpathy loop: hypothesis → change → assess → keep/revert), `research/program.md` (rules for what can/cannot change), package.json scripts `"research"` and `"research:score"`, `"type": "module"` and `serve` dev dep. Requires `lighthouse` global and `ANTHROPIC_API_KEY`.

## Lab Notes
- **Over-engineering before scoping:** Chris regularly scales back mid-session. Default to the smallest working version first. Ask scope before building.
- **Too many sequential Edits:** Read the file once, rewrite the whole thing in one Write call when making multiple changes.
- **Re-reading files repeatedly:** Read once, hold context, act.
- **Spinning before understanding:** Fully understand the problem before starting — ask one clarifying question if needed rather than building the wrong thing.
- **Context loss between sessions:** Always check for a CLAUDE.md or recent git log at session start to re-establish context without asking.
- **Measure before proposing:** When Chris reports a problem ("it's slow", "my SEO is bad"), run the real audit first — Lighthouse, chrome-devtools trace, grep, curl. Never propose a fix from intuition. If data shows the system is fine, say so. Chris pushes back hard on surgery aimed at the wrong patient.
- **Check skills first:** When a task falls into a domain with a dedicated skill, invoke it before answering from general knowledge. Chris notices when I skip it.
- **One call, not five options:** Make the recommendation, state the tradeoff, let Chris redirect. Lists of "you could do X, Y, Z, or W" are friction.
