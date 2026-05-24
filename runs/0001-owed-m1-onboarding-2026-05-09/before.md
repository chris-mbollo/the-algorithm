# Before: Owed M1 Onboarding (6 screens)

The first version of the Owed onboarding flow had **6 screens before the paywall**, all gathering information needed for *later* milestones (M4 claim generation, tracking, etc.) but blocking users from the value moment up front.

## Flow

1. **Welcome** — value prop + "Get started"
2. **Insurance card scan** — Anthropic Haiku parse of the photo
3. **Benefits form** — deductible $ + reimbursement %
4. **Therapist form** — name, NPI, ZIP, CPT code, frequency
5. **Estimate** — calculated reimbursement
6. **Paywall** — RevenueCat trial gate

## Friction inventory

| Field | Needed for | When user knows it |
|---|---|---|
| NPI (National Provider Identifier) | M4 CMS-1500 generation | Almost never |
| ZIP | M4 form prefill | When checked |
| CPT code | M4 procedure code | Almost never |
| Session frequency | Estimate accuracy | Approximately |
| OON deductible $ | Estimate math | Sometimes |
| Reimbursement % | Estimate math | Sometimes |
| Card scan | Convenience | Has card |

## Problem

Yadegari's viral rule for consumer onboarding is **3 seconds to value**. The flow was failing rule #1 — friction was placed *before* the value moment, not after.
