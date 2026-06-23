# Learning Management System

> If we ship an MCP-based agentic admin experience, design-partner administrators will complete a defined basket of recurring admin tasks ≥50% faster, at ≥92% accuracy on the gold set, with ≥60% stating intent to convert to a paid AI Admin seat at £250 Per Employee Per Month (PEPM) by end of Horizon 1 (H1).

---

## Strategy at a Glance

| Component | Module | Status | Key Artifact |
|-----------|--------|--------|-------------|
| **The Bet** | M1 | [x] | `01-the-bet/` |
| **The Moat** | M2 | [x] | `02-the-moat/` |
| **The Margin** | M3 | [x] | `03-the-margin/` |
| **The Contract** | M4 | [x] | `04-the-contract/` |
| **The Guardrails** | M5 | [x] | `05-the-guardrails/` |
| **The Pitch** | M6 | [x] | `06-the-pitch/` |

---

## The Bet (M1)

**What we're building, for whom, why now.**

- **Product:** Learning Management System
- **AI Value Archetype:** Orchestrator (Agentic)
- **Vulnerability Scores:** Moat 4/5 · Data 3/5 (lifts to 4/5 on H1 Network loop close) · Platform 2/5
- **Top Risk:** Encroachment by vertical LXP competitors targeting the Network Intelligence loop weakness, expressed as faster commercial growth
- **Confidence:** M-H (moved from M after prototype validation with 12 admin users across 5 design partners)
- **Prototype:** (https://app.eu.workato.com/?fid=smart-mcp_server)
- **Kill Criteria:** 1. Adoption: <40% of design-partner admins complete ≥3 sessions in any 2-week window during the 12-week beta. 2. Reliability: gold-set accuracy stays <85% for 4 consecutive weekly runs, OR hallucination >2% rolling 7-day with no improving trend. 3. Commercial: <2 of 5 design partners sign an LOI at £250 PEPM by H1 close, AND blended WTP below £150 PEPM.

→ Details: [`01-the-bet/`](01-the-bet/)

---

## The Moat (M2)

**Why this won't get copied in 6 months.**

- **Data Flywheel Score:** 15/20 post-H1 commitment (8/20 today)
- **Weakest Loop:** Preference loop (3/5 post-H1); cross-tenant preference inference is the H2 follow-on
- **Top Encroachment Threat:** Thrive LXP - 12 months to feature announcement, 18 months to enterprise-credible parity
- **Encroachment Defense:** Network Intelligence pipeline pulled forward into H1 (opt-in, anonymised, DPO and customer InfoSec sign-off), removing the structural narrative line the attacker would use
- **Vendor Portability:** Ready - 3 providers certified (Gemini, GPT-4o, Anthropic Claude), 1 swap rehearsed in test, no contractual lock-in

→ Details: [`02-the-moat/`](02-the-moat/)

---

## The Margin (M3)

**Will this make money or bleed it?**

- **Gross Margin (current):** £1.66 PEPM legacy admin seat - undifferentiated pricing, parity with end-user seats
- **Gross Margin (AI-adjusted):** ~71% on the AI Admin seat (£250 PEPM revenue, £71.15 PEPM COGS, £178.85 PEPM gross margin)
- **Pricing Model:** Hybrid - per-seat base price plus a per-seat fair-use ceiling (1,000 agent tasks per admin per month); overage at £0.15 per task
- **Pricing Today → Tomorrow:** £1.66 PEPM → £250 PEPM
- **Total AI COGS / unit:** £71.15 PEPM
- **Cascading Strategy:** Triage: GPT-4o (~90% of calls); frontier: Gemini (~10%); ratio 10:1; routing rule lives in the MCP server, not the prompt
- **Net Margin Shift:** Material on the AI Admin seat (~71% gross margin). Blended company-level shift meaningful but not dominant in year 1, since admin seats are a minority of the seat base. The AI Admin seat is a new high-margin revenue engine alongside the existing book, not a replacement.
- **Break-even at:** ~3 AI Admin seats per design-partner customer covers the H1 squad cost; full-programme break-even modelled at ~5,000 AI Admin seats sold (≤6 months post-GA at the modelled attach rate)

→ Details: [`03-the-margin/`](03-the-margin/)

---

## The Contract (M4)

**Why users will trust a probabilistic system.**

- **Reliability Target:** ≥92% on the gold set at the MCP layer; ≥95% on the two auto-permitted action categories (data return, group operations) where there is no human gate
- **Golden Dataset:** 220 rows, 46 adversarial today. Target ≥250 / ≥50 by H1 close; ≥500 / ≥100 by H2 close. Tagged per action category and per orchestrating model.
- **Confidence UX:** Tiered confidence + human-in-loop trigger. The M5 autonomy policy sits above the tier (policy is the floor; tiers gate within an action category).
- **HITL Architecture:** M5 autonomy policy is the floor. Confidence tiers gate within action categories; the policy gates across them. Sequence-aware gating added per the validated red-team finding.
- **Failure Mode Coverage:** Red-team finding (tool-chain composition bypass of the approval gate) validated in workshop and shipped a fix in H1 week 6: MCP policy gate now evaluates tool-call sequences within a session, not single calls; tenant auto-rules surfaced in the agent's planning step; 28 new gold-set rows added at ≥98% accuracy threshold.

→ Details: [`04-the-contract/`](04-the-contract/)

---

## The Guardrails (M5)

**What breaks when this scales - and what compounds.**

- **Compounding System:** All four loops active. Recursive Learning (Mixpanel telemetry → weekly gold-set additions). Cross-Domain Transfer (Intercom corrections → tool-description fixes). Network Intelligence (cross-tenant anonymised pipeline live H1). Preference Inference (tenant-level live, cross-tenant H2).
- **Governance Posture:** Policy covers AI assistance for administrators. Excludes learner-facing AI use cases (separate, future policy scope). DPIA completed and DPO-signed at H1 week 4.
- **Autonomy Boundaries:** Data return → auto (confidence-gated). Group ops → auto (confidence-gated, sequence-aware). Learning assignment → human approval required. User deletion → never auto.
- **Escalation Triggers:** Confidence <70% stops the task. Error/cancel rate +10% over 24h pauses the tenant. Hallucination ≥2% over 24h triggers auto-rollback. Tool-chain composition pattern matching an approval-bypass signature blocks at the MCP layer.
- **Audit Cadence:** Real-time (response-level guardrails). Daily (PM Mixpanel + Grafana review). Weekly (Product + Engineering triage). Quarterly (external audit-ready report).
- **Shadow AI Audit (user-side):** 11 workarounds found; 11 remediated by end of H1. Sanctioned estate consolidated to 7 tools. Net Shadow AI surface post-triage: 0 unsanctioned tools in active use. Hidden spend (£8-15k per year) replaced by consolidated sanctioned spend ~£22k per year.
- **Agent Boundaries:** Not shipping agents this version. The product is an MCP server orchestrated by the customer's choice of LLM client; we control the tools and gates, the customer's chosen LLM does the orchestration.
- **Regulatory Exposure:** **GDPR:** in scope, risk tier minimal, MCP-layer permission enforcement. **EU AI Act:** *limited risk* classification, transparency met via tool-call trace exposure. **Data residency:** EU customer data stays in EU-hosted infrastructure throughout the iPaaS + MCP + model-vendor path.

→ Details: [`05-the-guardrails/`](05-the-guardrails/)

---

## The Pitch (M6)

**How you get this funded, shipped, and adopted.**

- **Horizon 1 (Now):** Closed-beta MCP Admin Agent with 5-10 design partners · Reliability instrumentation live in production behind a feature flag · **Network Intelligence pipeline live (pulled forward from H2)** · Shadow AI audit complete and triaged to zero unsanctioned tools
- **Horizon 2 (Next):** GA launch of the AI Admin seat at £250 PEPM with M5 autonomy policy and reliability contract live · Cross-tenant preference inference · Gold-set scale to ≥500 rows / ≥100 adversarial
- **Horizon 3 (Bet):** Unified workforce-platform orchestrator - one agent reasoning across the learning, performance, and talent modules, executing multi-module workflows
- **Board Narrative:** The most defensible AI revenue in enterprise workforce software is the administrative layer, and a 12-month window exists to take it before LXP attackers close the gap or big-tech platforms encroach.
- **Ask:** 1. Strategic alignment - "are we in or out" on the bet, no half-commitment. 2. Build funding for H1 and H2 in full, sized to revenue inflection at H2 close. 3. Explicit board sign-off on the binary kill criteria so the wind-down path is agreed up-front, not in the moment.
- **Key Strategic Change:** Network Intelligence loop fix pulled from H2 into H1. Same fix closes three separate gaps (M2 weakest flywheel input, M4 gold-set coverage gap, M5 missing compounding loop). Highest-leverage single investment in the strategy.

→ Details: [`06-the-pitch/`](06-the-pitch/)
