# After: Owed M1 Onboarding (2 screens)

Refactored to **2 screens before paywall**. All field-gathering deferred to "just-in-time" — fields appear only at the moment they're actually needed (first session log, first claim submit, etc.).

## Flow

1. **Screen 1 — "How much do you pay per therapy session?"**
   - Session price input
   - Insurer dropdown
   - Big primary button: **"Show me what I get back"**

2. **Screen 2 — Estimate**
   - "**$3,400/year owed to you.**"
   - Primary button: **"Start tracking — 3 days free"**

3. **Paywall** (RevenueCat trial gate)

## Defaults that made the cut possible

| Field | Default |
|---|---|
| CPT code | `90837` (60-min, modal value) |
| Session frequency | 1× / week (median Sarah) |
| Deductible / % | Per-insurer typical table (Cigna PPO ≈ $1500 / 60%, etc.) — labeled *"Most {Cigna} plans"* so user can override |
| NPI / ZIP / Group ID | Removed from onboarding entirely — collected at M4 |
| Card scan | Moved to *post-paywall* as "Set up tracking" |

## Copy rewrites (3rd-grade test)

A handful that shipped:
- "Confirm your benefits" → "Tell us about your insurance"
- "OON deductible ($)" → "How much you pay before insurance starts helping"
- "Reimbursement %" → "How much insurance pays back"
- "CMS-1500 claim forms" → "the form your insurance needs"
- "superbills" → "receipts"
- "Continue without trial" → "Maybe later"

## Shipped

Refactor was applied in the same session — Chris said "do it" and the flow collapsed to 2 screens.
