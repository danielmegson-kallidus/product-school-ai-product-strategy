# Three-Horizon Roadmap & Board Pitch

> Context: investor-board framing. Numbers shown are illustrative ranges, anchored to the unit economics already proven in Module 3 (M3): Cost of Goods Sold (COGS) of £71.15 Per Employee Per Month (PEPM), proposed Artificial Intelligence (AI) Admin seat price of £250 PEPM, ~70% gross margin holding through a 3x inference-cost stress test.

## Roadmap

### Horizon 1 - Now (0-3 months)
*Quick wins. Ship with existing capabilities.*

| Initiative | Metric | Confidence |
|-----------|--------|-----------|
| Closed-beta of the Model Context Protocol (MCP) Admin Agent with 5-10 design-partner customers, on the existing Workato + Admin Application Programming Interface (API) stack | Admin task-time reduction (target ≥50% on a defined task basket); beta Net Promoter Score (NPS) ≥30; 90-day beta-to-paid intent ≥60% | H |
| Reliability instrumentation live - the Module 4 (M4) contract running in production behind a feature flag | 92% accuracy on gold set, <1% hallucination rate, p95 latency <2s read / <5s write, all measured weekly | H |

### Horizon 2 - Next (3-9 months)
*Bets. Requires new capabilities or integrations.*

| Initiative | Metric | Confidence |
|-----------|--------|-----------|
| General Availability (GA) launch of the AI Admin seat at £250 PEPM, with the Module 5 (M5) autonomy policy and reliability contract live | AI Admin seat attach rate ≥25% of new contracts; meaningful Annual Recurring Revenue (ARR) run-rate from AI seats; gross margin holds ≥65% under realised cascade mix | M |
| Network Intelligence loop fix - opt-in cross-tenant anonymised gold-set pipeline (closes the M2 weakest flywheel input, 1/5) | ≥60% of customers opted-in within 6 months; ≥30% of new gold-set rows sourced cross-tenant; regression lead-time improved by ≥14 days | M |

### Horizon 3 - Bet (9-18 months)
*Moonshots. High uncertainty, high potential.*

| Initiative | Metric | Confidence |
|-----------|--------|-----------|
| Unified workforce-platform orchestrator - one agent reasoning across the learning management, performance management, and talent management modules, executing multi-module workflows (e.g. correlating overdue compliance training with a manager's goal-setting cadence and proposing an integrated intervention) | Multi-module session ratio ≥35% of admin sessions; expansion ARR from multi-module customers; Net Revenue Retention (NRR) lift ≥10 percentage points on AI Admin cohort; cross-module gross margin held in the proven band | L |

## Board Pitch

**Thesis (1 sentence):** The most defensible AI revenue in enterprise workforce software is the administrative layer, and a 12-month window exists to take it before Learning Experience Platform (LXP) attackers close the gap or big-tech platforms encroach.

**The case:**
1. **Why now:** Three signals are converging. The MCP standard is maturing fast across Anthropic, OpenAI, and Google, removing the vendor-lock risk that previously made agent-orchestration bets fragile. Customer demand for administrative productivity is acute - the ongoing BusinessObjects-to-Power-BI reporting migration across the customer base is a leading indicator of admin-side appetite for "AI does the report for me". And the named attackers (Thrive, Learning Pool) are ~12 months behind on contextual depth per M2, but closing.
2. **What's defensible:** Contextual moat scores 4/5 (multi-year contracts, deep admin workflow embedment, complex on-and-offboarding). Historic data advantage 3/5 (cumulative customer telemetry feeds modelling that newer entrants cannot match). The autonomy policy gates are enforced server-side at the MCP layer, not in the orchestrating Large Language Model's (LLM's) prompt - which means a competitor cannot replicate the reliability posture without rebuilding the underlying permissions and data-scope model. Model-agnostic architecture (M2 kill-switch ready) keeps us off any single vendor's hook.
3. **The economics:** Current administrator seat sells at £1.66 PEPM. The proposed AI Admin seat sells at £250 PEPM with £71.15 PEPM COGS, delivering ~70% gross margin. Under the M3 stress test, the unit economics survive a 3x inference-cost shock (margin compresses to ~10%, still positive), a doubling of the heaviest-usage segment (margin to 50%), and a 50% model-vendor price hike (margin to 50%). Administrators are a minority of the seat base, so blended company-level margin shift is modest - but a high-margin AI Admin revenue engine emerges alongside the existing book.

**The risks:**
1. **Trust / failure modes:** Probabilistic system operating adjacent to regulated workflows (General Data Protection Regulation (GDPR) data, compliance training, audit obligations). Mitigated by the M4 reliability contract (auto-rollback at ≥2% hallucination, gold-set audits on drift) and M5 autonomy boundaries (assignment requires human approval, user deletion never auto). The reliability discipline is itself a competitive moat - it is what lets enterprise buyers say yes.
2. **Scale / governance:** Today the Network Intelligence flywheel loop scores 1/5 - we do not yet learn across the customer base. The H2 cross-tenant anonymisation build is on the critical path; without it, the data advantage decays as competitors accumulate scale. EU AI Act exposure is currently *limited risk* but moves up a tier if the agent ever takes adverse decisions on individual learners, which the M5 policy explicitly prevents.
3. **Competitive:** LXP attackers (Thrive, Learning Pool) are targeting our weakest loop with a stronger AI / data narrative but shallower workflow depth. ~5-10% of value at risk over 12 months per M2. Big-tech encroachment is the lower-probability tail risk (2/5 on M1 platform exposure) - if Apple, Google, or OpenAI ship a native administrative agent it is survivable on workflow specificity, but the moat is narrower.

**The ask:**
1. **Strategic alignment - "are we in or out" on this bet.** A 12-month window does not survive a half-commitment. We are asking the board to commit explicitly to the thesis, not to defer to a stage-gate next quarter.
2. **Build funding for H1 and H2 in full.** Scope covers design-partner operations through closed beta, reliability instrumentation in production, GA launch including pricing rollout and commercial enablement, and the Network Intelligence loop fix. Quantum to be agreed against a detailed plan, but sized to fund the stream through to revenue inflection at end of H2 without re-approval.

## M1 Baseline vs. Now

**M1 baseline:**
We are building a Model Context Protocol server that lets administrators use the Learning Management System (LMS) through a chat-based AI client, replacing manual administrative workflows with conversational ones. We expect this to deliver an improved user experience and a measurable reduction in administrative task burden. Our confidence is moderate, with contextual moat 4/5, data advantage 3/5, and platform exposure 2/5, against three named attackers (Thrive, Learning Pool, Cornerstone OnDemand).

**Now:**
We are commercialising the administrative layer of enterprise workforce software as an agent-orchestrated, premium-priced surface, defended by a server-side autonomy policy and a measurable reliability contract that competitors cannot quickly replicate. The unit economics work at ~70% gross margin and survive a 3x inference-cost stress test, and the cross-tenant learning loop scheduled in H2 closes our weakest data flywheel input within nine months. Confidence has moved from M to M-H based on prototype validation, completed reliability and governance design, and a clear 12-month window before the named attackers reach feature parity.
