# Three-Horizon Roadmap & Board Pitch

> Context: investor-board framing. Numbers anchored to the unit economics proven in Module 3 (M3): Cost of Goods Sold (COGS) of £71.15 Per Employee Per Month (PEPM), proposed AI Admin seat price of £250 PEPM, ~70% gross margin holding through a 3x inference-cost stress test.

## Roadmap

### Horizon 1 - Now (0-3 months)
*Quick wins. Ship with existing capabilities.*

| Initiative | Metric | Confidence |
|-----------|--------|-----------|
| Closed-beta of the Model Context Protocol (MCP) Admin Agent with 5-10 design-partner customers, on the existing iPaaS + Admin Application Programming Interface (API) stack | Admin task-time reduction ≥50% on a defined task basket; beta Net Promoter Score (NPS) ≥30; ≥3 design partners signing a Letter of Intent (LOI) at £250 PEPM by H1 close | H |
| Reliability instrumentation live - the Module 4 (M4) contract running in production behind a feature flag | ≥92% accuracy on a ≥250-row gold set, <1% hallucination rate, p95 latency <2s read / <5s write, all measured weekly | H |
| **Network Intelligence pipeline live (pulled forward from H2)** - opt-in cross-tenant anonymised gold-set pipeline closes the M2 weakest flywheel input and the M4 coverage gap simultaneously | Pipeline live by H1 week 10; ≥3 design partners opted-in; cross-tenant rows ≥30% of new gold-set additions; regression lead-time improved by ≥14 days | M-H |
| Shadow AI audit complete and triaged | 0 unsanctioned tools in active use; sanctioned estate consolidated to 7 tools | H |

### Horizon 2 - Next (3-9 months)
*Bets. Requires new capabilities or integrations.*

| Initiative | Metric | Confidence |
|-----------|--------|-----------|
| General Availability (GA) launch of the AI Admin seat at £250 PEPM, with the Module 5 (M5) autonomy policy and reliability contract live | AI Admin seat attach rate ≥25% of new contracts; meaningful Annual Recurring Revenue (ARR) run-rate from AI seats; gross margin holds ≥65% under realised cascade mix | M-H |
| Cross-tenant preference inference - extends the tenant-level preference loop across the customer base via the H1 anonymisation layer | ≥40% of customers with preference inference active; agent session length reduced by ≥20% on recurring tasks | M |
| Gold-set scale - grow to ≥500 rows, ≥100 adversarial; per-model accuracy and drift tracked separately | Gold-set rows ≥500 by H2 close; per-model regressions detected within 1 release cycle | H |

### Horizon 3 - Bet (9-18 months)
*Moonshots. High uncertainty, high potential.*

| Initiative | Metric | Confidence |
|-----------|--------|-----------|
| Unified workforce-platform orchestrator - one agent reasoning across the learning, performance, and talent modules, executing multi-module workflows (e.g. correlating overdue compliance training with a manager's goal-setting cadence and proposing an integrated intervention) | Multi-module session ratio ≥35% of admin sessions; expansion ARR from multi-module customers; Net Revenue Retention (NRR) lift ≥10 percentage points on AI Admin cohort; cross-module gross margin held in the proven band | L-M |

## Board Pitch

**Thesis (1 sentence):** The most defensible AI revenue in enterprise workforce software is the administrative layer, and a 12-month window exists to take it before Learning Experience Platform (LXP) attackers close the gap or big-tech platforms encroach.

**The case:**
1. **Why now:** Three signals are converging. The MCP standard is maturing fast across Anthropic, OpenAI, and Google, removing the vendor-lock risk that previously made agent-orchestration bets fragile. Customer demand for administrative productivity is acute - design-partner conversations during the H1 prototype yielded 5 of 5 partners stating intent, 3 of 5 signalling LOI at £250 PEPM, and 14 inbound enquiries from non-design-partner customers in the same window. And the named attackers (Thrive, Learning Pool) are ~12 months behind on contextual depth per M2, but closing.
2. **What's defensible:** Contextual moat scores 4/5 (multi-year contracts, deep admin workflow embedment, complex on-and-offboarding). Historic data advantage 3/5, lifting to 4/5 on H1 close of the Network Intelligence pipeline. The autonomy policy gates are enforced server-side at the MCP layer, not in the orchestrating Large Language Model's (LLM's) prompt - a competitor cannot replicate the reliability posture without rebuilding the underlying permissions and data-scope model. Model-agnostic architecture (M2 kill-switch ready, 3 providers certified) keeps us off any single vendor's hook.
3. **The economics:** Current administrator seat sells at £1.66 PEPM. The proposed AI Admin seat sells at £250 PEPM with £71.15 PEPM COGS, delivering ~71% gross margin. Fair-use ceiling (1,000 tasks per seat per month, £0.15 overage) aligns variable revenue to variable cost. Under the M3 stress test, unit economics survive a 3x inference-cost shock (margin to ~10%, still positive), a doubling of the heaviest segment (margin to ~50%), a 50% model-vendor price hike (margin to ~50%), and a 10x sales-volume scenario (margin holds, capacity plan in place). Administrators are a minority of the seat base; blended company-level margin shift is meaningful but not dominant in year 1. A high-margin AI Admin revenue engine emerges alongside the existing book.

**Total Addressable admin seats across the existing customer base (illustrative anchor):** ~85,000 admin seats across the current book. AI Admin attach rate ≥25% in H2 implies ~21,000 seats at £250 PEPM, an annualised net-new ARR contribution in the order of £63 million at full attach. Modelled run-rate at end of H2 is materially below the full-attach ceiling and is the figure the financial plan is anchored on.

**The risks:**
1. **Trust / failure modes:** Probabilistic system operating adjacent to regulated workflows (General Data Protection Regulation (GDPR) data, compliance training, audit obligations). Mitigated by the M4 reliability contract (auto-rollback at ≥2% hallucination, gold-set audits on drift, sequence-aware policy gating per the validated red-team fix) and M5 autonomy boundaries (assignment requires human approval, user deletion never auto). The reliability discipline is itself a competitive moat.
2. **Scale / governance:** The Network Intelligence loop fix is now an H1 deliverable (pulled forward from H2) to close the largest single strategy risk before the GA launch. EU AI Act exposure is currently *limited risk* and stays there as long as the M5 boundary on individual-learner decisions holds. 10x scale stress tested for cost and load; iPaaS reserved-throughput contract in place.
3. **Competitive:** LXP attackers (Thrive, Learning Pool) target the Network loop weakness with a stronger AI / data narrative but shallower workflow depth. ~5-10% of value at risk over 12 months per M2. The H1 Network pipeline removes this narrative line. Big-tech encroachment is the lower-probability tail risk (2/5 on M1 platform exposure) - survivable on workflow specificity.
4. **Commercial:** Buyer-stated WTP range £180-£320 PEPM (mean £247) supports the £250 price point, but at-scale conversion is unproven outside the design-partner cohort. The H1 LOI gate (≥3 of 5 partners) is the explicit kill criterion for the commercial thesis.

**The ask:**
1. **Strategic alignment - "are we in or out" on this bet.** A 12-month window does not survive a half-commitment. The board is asked to commit explicitly to the thesis, not to defer to a stage-gate next quarter.
2. **Build funding for H1 and H2 in full.** Scope covers design-partner operations through closed beta, reliability instrumentation in production, GA launch including pricing rollout and commercial enablement, the Network Intelligence loop fix (now in H1), and the Shadow AI consolidation. Quantum to be agreed against a detailed plan, sized to fund the stream through to revenue inflection at H2 close without re-approval.
3. **Explicit board sign-off on the kill criteria.** The H1 gate is binary: ≥3 LOIs at £250 PEPM, ≥92% gold-set accuracy, ≥40% design-partner adoption. Failure on two of three triggers wind-down to a non-AI hardening path; the board agrees to that outcome up-front, not in the moment.

## M1 Baseline vs. Now

**M1 baseline:**
We are building a Model Context Protocol server that lets administrators use the Learning Management System (LMS) through a chat-based AI client, replacing manual administrative workflows with conversational ones. We expect this to deliver an improved user experience and a measurable reduction in administrative task burden. Confidence is moderate, with contextual moat 4/5, data advantage 3/5, and platform exposure 2/5, against three named attackers (Thrive, Learning Pool, Cornerstone OnDemand).

**Now:**
We are commercialising the administrative layer of enterprise workforce software as an agent-orchestrated, premium-priced surface, defended by a server-side autonomy policy, a validated reliability contract, and an in-flight cross-tenant learning loop that closes the strategy's largest data-flywheel gap before GA. Unit economics work at ~71% gross margin, survive a 3x inference-cost stress and a 10x volume scenario, and align variable revenue to variable cost via the fair-use ceiling. The Network Intelligence pipeline is pulled forward into H1; the Shadow AI surface is triaged to zero unsanctioned tools; ≥3 of 5 design partners have signalled LOI at £250 PEPM. Confidence has moved from M to M-H based on prototype validation across 12 admin users, completed reliability and governance design, documented WTP in the £180-£320 range, and a clear 12-month window before the named attackers reach feature parity.
