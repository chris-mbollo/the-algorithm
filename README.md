# The Algorithm

A skill for [Claude Code](https://claude.com/claude-code) that pressure-tests anything — code, configs, prompts, architectures, workflows, business processes — through Elon Musk's five-step engineering algorithm.

> *"You want fewer things, not more."*

## What it does

Point it at anything. It tells you what to delete, what to simplify, and what's actually earning its place. Every audit is structured:

1. **Make the requirements less dumb** — who asked for this? Evidence?
2. **Try very hard to delete** — what breaks if it just doesn't exist?
3. **Simplify** — fewer lines, fewer dependencies, fewer moving parts
4. **Accelerate** — only after deletion + simplification
5. **Automate** — only after the process is stable

Plus: idiot index (cost ÷ value), utility multiplier (impact × audience), and theoretically-perfect-product check.

## Install

Copy [`SKILL.md`](./SKILL.md) into `~/.claude/skills/the-algorithm/SKILL.md`. In Claude Code: *"run the algorithm on X"* invokes it.

---

## Receipts

Every run gets a folder under [`runs/`](./runs) with `before.md`, `after.md`, `audit.md`, `metrics.json`. The git log is the run log.

### Totals
- **Runs:** 2
- **Shipped:** 2 / 2
- **By target type:** 1 UX flow · 1 config file
- **Highlights:** 67% fewer onboarding screens · 30% fewer lines in global CLAUDE.md

### Log

| # | Date | Target | Type | Headline | Folder |
|---|---|---|---|---|---|
| 0001 | 2026-05-09 | Owed M1 onboarding | ux-flow | 6 → 2 screens before paywall (-67%) | [run](./runs/0001-owed-m1-onboarding-2026-05-09) |
| 0002 | 2026-05-24 | `~/CLAUDE.md` | config-file | 56 → 39 lines (-30%) | [run](./runs/0002-claude-md-2026-05-24) |

---

## Adding a run

```bash
./bin/algo-log new <target-slug>
```

Creates the next-numbered folder under `runs/` with stub files. Fill in `before.md` / `after.md` / `audit.md` / `metrics.json`, then commit.

## Why this repo exists

I'm building in public. The algorithm is my favorite tool for fighting feature creep, config bloat, and dependency hoarding. Every receipt here is a real audit on something I own — not a toy example.

If you find a target you want me to run it on, open an issue.

— [@chrismbollo](https://github.com/chris-mbollo)
