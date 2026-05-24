# Algorithm Audit: Owed M1 Onboarding vs. Yadegari's Viral Rules

**Date:** 2026-05-09
**Target:** Owed iOS onboarding flow (Expo + RevenueCat)
**Headline metric:** 6 screens → 2 screens before paywall (**~67% friction reduction**)

The flow as-built was **6 screens before the $ moment**. Yadegari's bar is **3 seconds**. Failing rule #1.

---

## Step 1: Requirements Check (every screen as a requirement)

| Screen | Who asked? | Verdict |
|---|---|---|
| Welcome | Industry default | **SUSPECT** — every extra screen pre-value drops 10–20% of users |
| Card scan | SPEC.md hook | **SUSPECT** — asking for ID before showing value is backwards |
| Benefits form (deductible/%) | Recovery estimate needs the inputs | **SUSPECT** — Sarah often doesn't know these. Friction wall. |
| Therapist form (name, NPI, ZIP, CPT, frequency) | M4 CMS-1500 prefill | **DUMB** — M4 needs it. M1 doesn't. Asking now = premature. |
| Estimate | Trial conversion hook (SPEC) | **VALIDATED** — this *is* the value moment |
| Paywall | RevenueCat trial gate | **VALIDATED** — required |

**The fundamental error:** friction placed *before* the value. Yadegari's whole point is the opposite.

## Step 2: Deletion Candidates

Delete from M1, defer to "just-in-time":

- **NPI field** → delete. Needed only when generating CMS-1500 (M4). Ask then.
- **ZIP code** → delete. Same reason.
- **CPT code picker** → delete. Default to `90837`.
- **Session frequency picker** → delete. Default `1x/week`.
- **Group ID** → delete from onboarding.
- **Card scan as Step 1** → move to *post-paywall*.
- **"Confirm your benefits" call-script screen** → delete from M1. Use per-insurer typicals.

10% rule: the deductible % field probably comes back as an inline override on the estimate screen for users with non-standard plans. That's fine.

## Step 3: Simplification (copy rewrites for 3rd-grader test)

| Current | Rewritten |
|---|---|
| "Confirm your benefits" | "Tell us about your insurance" |
| "OON deductible ($)" | "How much you pay before insurance starts helping" |
| "Reimbursement %" | "How much insurance pays back" |
| "CMS-1500 claim forms" | "the form your insurance needs" |
| "NPI" | (deleted) |
| "superbills" | "receipts" |
| "timely filing" | "before the deadline" |
| "Track every claim through 5 states until the deposit lands." | "We follow your money until it hits your bank." |
| "See your live deductible meter and YTD recovered." | "See how much you've gotten back this year." |
| "no win-backs, no friction" | "Cancel any time. We won't beg." |
| "Skip and enter manually" | "I don't have my card right now" |
| "Continue without trial" | "Maybe later" |

## Step 4: Accelerate — constraint is **time-to-$X**

Theoretical minimum: **2 screens before paywall.**

```
Screen 1 — "How much do you pay per therapy session?"
  [ $200 ]
  Insurance: [ Cigna ▼ ]
  → "Show me what I get back"

Screen 2 — "$3,400/year owed to you."
  → "Start tracking — 3 days free"

Screen 3 — Paywall
```

**Estimated impact:** 6 → 2 screens ≈ 40% lift in trial-start rate.

## Step 5: Automation Assessment

Don't automate yet. But default smartly:
- **Per-insurer typical benefits table** as defaults (Cigna PPO ≈ $1500/60%, Aetna PPO ≈ $1000/70%, etc.)
- **Card-scan auto-parse** can fill these too, but it's not on the critical path anymore.

## Idiot Index

| Cost | Per onboarded user | Notes |
|---|---|---|
| Anthropic Haiku card parse | ~$0.001 | Cheap |
| User attention | **3 min × ~60% completion** | This is the actual cost |
| LTV at 6-week median retention | ~$30 | |

Dollar idiot index is fine. **Attention idiot index is bad** — charging 3 minutes for a 30-second estimate.

## Utility Multiplier

- Improvement per Sarah who completes: $200–500/yr recovered (real, measurable)
- Affected: ~5M US OON therapy patients
- Cutting onboarding 3× roughly doubles finishers → **~2× total utility delivered** for the same product.

## Theoretically Perfect Version

> "Therapy session price?" [ $___ ] [Insurance ▼]
>
> "**$3,400 owed to you this year.** Start tracking →"

Three seconds to demonstrate value. One unmistakable button.

---

## Summary: Do This Now

1. **Move card scan AFTER paywall.** Surface later as "Set up tracking."
2. **Default everything that has a sane default.** CPT → 90837. Frequency → weekly. Deductible/% → per-insurer typicals. Drop NPI, ZIP, group ID from M1.
3. **Rewrite all copy at 3rd-grade level.** Two-pass: ship the new strings, then read them aloud.
4. **Reorder to 2 pre-paywall screens.**
5. **Every primary button names what the user gets**, not what the system does.

## Outcome

Shipped same session — Chris said "do it" and the refactor went in.
