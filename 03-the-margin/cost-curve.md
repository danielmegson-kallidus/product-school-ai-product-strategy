# Cost Curve & Pricing Strategy

## Cost Model

| Cost Category | Per-User/Month | Notes |
|--------------|----------------|-------|
| Inference (primary model) | £50.00 | Gemini frontier, ~10% of calls |
| Inference (cascading/triage) | £20.00 | GPT-4o triage, ~90% of calls |
| Infrastructure | £0.15 | MCP server, iPaaS, observability stack |
| Data/storage | £0.00 | Included in Infra |
| Human-in-the-loop | £1.00 | Triage squad (eval review, escalations) |
| **Total AI COGS** | £71.15 | Sum of above |

## Cascading Strategy
Triage model handles deterministic single-tool calls and grounded read operations; frontier model invoked only for multi-step reasoning, ambiguous user intent, or write actions requiring composition.

**Triage model:** GPT-4o
**Frontier model:** Gemini
**Routing rule:** Triage by default. Escalate to frontier on (a) confidence <80% at first pass, (b) ≥2 tool calls in a chain, (c) any write action.
**Expected cascade ratio:** 10:1 (10 triage calls per 1 frontier call). Achieved ratio measured weekly; routing rule re-tuned if drift >2 points.

## Pricing Model

**Current pricing:** £1.66 PEPM (legacy admin seat)
**Proposed AI pricing:** £250 PEPM (AI Admin seat) with a fair-use ceiling
**Model:** Hybrid - per-seat base price plus a per-seat task ceiling (1,000 agent tasks per admin per month). Overage at £0.15 per task. Aligns variable revenue to variable cost; prevents a single power-user burning seat-level margin.

**Willingness-to-pay (WTP) evidence:**
• Design-partner pricing conversations completed with 5 of 5 partners during prototype testing. Indicative buyer-stated WTP range: £180-£320 PEPM, blended mean £247 PEPM.
• 3 of 5 design partners have signalled intent to sign a Letter of Intent (LOI) at £250 PEPM at H1 close, subject to reliability-contract publication and the fair-use ceiling.
• Top-of-funnel signal: 14 inbound enquiries from non-design-partner customers across the H1 window, citing admin productivity as the top priority for next renewal.

## Stress Tests

| Scenario | Impact on Margin | Response |
|----------|-----------------|----------|
| Inference costs 3x | Reduces margin to ~10% | Survivable. Triggers cascade re-tune (target 15:1) and fair-use ceiling enforcement. |
| Heaviest segment doubles | Reduces margin to ~50% | Survivable. Fair-use ceiling caps the worst case; overage pricing recovers cost. |
| Model provider raises prices 50% | Reduces margin to ~50% | Survivable. M2 kill-switch swap rehearsed; cascade re-tuned post-swap. |
| 10x scale (10x admin seats sold) | Margin holds at ~70%; absolute COGS scales linearly. Latency p95 holds <2s read / <5s write (load-tested at 5x; 10x test scheduled H1 week 8). | Capacity plan in place. Bottleneck risk: iPaaS rate limits, mitigated by reserved-throughput contract with the iPaaS vendor. |
| Frontier model deprecated by vendor | <2 week recovery | Promote certified Anthropic Claude provider per the M2 kill-switch runbook. Re-baseline gold-set eval. |

## Board One-Pager
**Before (traditional SaaS):** Admin seats and end-user seats priced at parity (£1.66 PEPM). Admin value undifferentiated; admin productivity treated as a cost centre by buyers.

**After (AI-enabled):** Admin seats repositioned at £250 PEPM as an AI Admin product, with a fair-use ceiling aligning variable revenue to variable cost. Justified by provable ROI - ≥50% admin task-time reduction in the design-partner cohort, ≥92% gold-set accuracy, full reliability contract published externally. Buyer-stated WTP (£180-£320 PEPM range, mean £247) supports the price point. Fair-use ceiling protects against unbounded inference exposure on power users.

**Net margin shift:** Net margin shift is material on the AI Admin seat (£178.85 gross margin per seat per month against £71.15 COGS, ~71% margin). Blended company-level shift is meaningful but not dominant in year 1, since admin seats are a minority of the seat base. The AI Admin seat is a new high-margin revenue engine running alongside the existing book, not a replacement of it. Modelled run-rate at end of H2: AI Admin attach rate ≥25% of new contracts, with a path to ≥40% by end of H3.
