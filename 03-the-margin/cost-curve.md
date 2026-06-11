# Cost Curve & Pricing Strategy

## Cost Model

| Cost Category | Per-User/Month | Notes |
|--------------|----------------|-------|
| Inference (primary model) | £50.00 | Gemini |
| Inference (cascading/triage) | £20.00 | GPT4-0 |
| Infrastructure | £0.15 | Varied |
| Data/storage | £0.00 | Included in Infra |
| Human-in-the-loop | £1.00 | For squad |
| **Total AI COGS** | £71.15 | Added from above |

## Cascading Strategy
<!-- Cheap model → frontier model routing logic -->

**Triage model:** GPT 4-0
**Frontier model:** Gemini
**Routing rule:** Balanced
**Expected cascade ratio:** 10:1

## Pricing Model

**Current pricing:** £1.66 PEPM
**Proposed AI pricing:** £250 PEPM
**Model:** hybrid (seat-based)

## Stress Tests

| Scenario | Impact on Margin | Response |
|----------|-----------------|----------|
| Inference costs 3x | Reduces margin to 10% | Survivable |
| Heaviest segment doubles | Reduces margin to 50% | Survivable |
| Model provider raises prices 50% | Reduces Margin to 50% | Survivable |

## Board One-Pager
<!-- Before/After: Old SaaS revenue vs. AI usage revenue for your product -->

**Before (traditional SaaS):** In our traditional SaaS model, our per-user seat was the same for Admins and Users.
**After (AI-enabled):** We will position Admin seats at a far higher price-point, justified by provable ROI to customer in 10x effort reduction in System Admin. Our AI enabled model allows us to prove real value but de-risked. We will protect against overspend via an enforced fair-usage policy. We will paint the value as being of benefit to a limited pool.
**Net margin shift:** Net margin shift is significant for this user persona. Net impact as a whole is minimal, as Admins are a minority population.
