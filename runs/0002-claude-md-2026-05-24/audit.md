# Algorithm Audit: /Users/macbookpro/CLAUDE.md

**Date:** 2026-05-24
**Target:** Project-level CLAUDE.md (loaded into every Claude Code conversation)
**Headline metric:** 56 lines → 39 lines (**30% cut**)

---

## Step 1: Requirements Check

| Section | Verdict | Reasoning |
|---|---|---|
| About this repo | VALIDATED | Prevents the real failure of committing at $HOME |
| Profile — Priorities + Comms style | VALIDATED | Shapes every reply |
| Profile — Sales backstory / YouTube / Content vs Capital / DEA | SUSPECT | Identity, not workflow. When does this change what Claude does? |
| Skills routing | VALIDATED | Direct triggers |
| Design References — Godly | SUSPECT | When was the last time I actually pulled a Godly ref? |
| Design References — 21st.dev / magic MCP | VALIDATED | Used often |
| Projects — names/paths/stacks | VALIDATED | Navigation aid |
| Projects — status dates ("V1 shipped 2026-05-06", "Pre-code roadmap") | DUMB | Rots within weeks. Memory already tracks this |
| New Project Checklist — SPEC.md + Local CLAUDE.md | VALIDATED | Real ritual |
| New Project Checklist — Auto research block | SUSPECT | 3 dense lines for a workflow that fires on one project type |
| Lab Note — Over-engineering / Spinning before understanding | VALIDATED | Real failure modes |
| Lab Note — Measure before proposing | VALIDATED | But duplicated in memory |
| Lab Note — Check skills first | DUMB | superpowers system prompt already enforces this. Belt + suspenders |
| Lab Note — Context loss between sessions | DUMB | This rule lives inside the file that solves it. Recursive |
| Lab Note — One call, not five options | DUMB | Already in Profile comms style 8 lines above |
| Lab Note — Too many sequential Edits / Re-read files | SUSPECT | Old-Claude-tax. Modern Claude does this by default |

## Step 2: Deletion Candidates

**Deleted now (high confidence):**
1. "Check skills first" Lab Note — superpowers system prompt already blocks responses without skill checks
2. "Context loss between sessions" Lab Note — self-referential
3. "One call, not five options" Lab Note — duplicates Profile comms style
4. All status dates in Projects — memory tracks this, dates rot

**Deleted probably (10% might come back):**
5. Profile narrative paragraph — sales career, YouTube/X/Instagram, Content vs Capital. Kept priorities + comms style.
6. "Too many sequential Edits" + "Re-reading files repeatedly" — these were 2024 problems
7. Godly reference

**Moved, not deleted:**
8. Auto research block — extracted to `~/.claude/templates/auto-research.md`

## Step 3: Simplifications

- **Projects:** prose with `·` separators → tight one-liners
- **Skills:** 4 bullets → 1 line
- **New Project Checklist:** 4 items → 3 (merged SPEC.md + Local CLAUDE.md)

## Step 4: Acceleration

The constraint was signal density. CLAUDE.md loads into every conversation — every dead line is permanent tax. Cutting noise accelerates context load and improves signal-to-noise on every future turn.

## Step 5: Automation

N/A — CLAUDE.md is a curated artifact, not generated. Re-run this audit quarterly by hand.

## Idiot Index

CLAUDE.md cost = (lines × every conversation forever). Lab Notes that fire <5% of sessions but cost 100% of loads = high idiot index. Three Lab Notes failed this test (the three DUMB-flagged).

## Result

| Metric | Before | After | Delta |
|---|---|---|---|
| Total lines | 56 | 39 | -30% |
| Lab Notes | 8 | 3 | -63% |
| Projects metadata lines | 10 | 10 | unchanged (compressed in place) |
| Sections | 7 | 7 | unchanged |
| Templates created | 0 | 1 | `auto-research.md` |

Every line that survived is doing work I can name.
