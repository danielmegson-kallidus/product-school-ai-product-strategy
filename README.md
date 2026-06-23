# Learning Management System

> By adding an MCP Server capability, Administrators will have an improved user experience and reduction in task.

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
- **AI Value Archetype:** Orchastrator for Agentic
- **Vulnerability Scores:** Moat 4/5 · Data 3/5 · Platform 2/5
- **Top Risk:** Faster growth by competitors
- **Confidence:** M
- **Prototype:** (https://app.eu.workato.com/?fid=smart-mcp_server)
- **Kill Criteria:** - Lack of positive response from prototype. - Lack of adoption from early beta. - Massively positive response from prototype; shows we have found a product solution fit.

→ Details: [`01-the-bet/`](01-the-bet/)

---

## The Moat (M2)

**Why this won't get copied in 6 months.**

- **Data Flywheel Score:** 8/20
- **Weakest Loop:** Network loop
- **Top Encroachment Threat:** Thrive LXP
- **Encroachment Defense:** Add model context from multiple customers to blind-inform model based on randomisation, with opt out for customers who do not wish for data to be used this way.
- **Vendor Portability:** Ready

→ Details: [`02-the-moat/`](02-the-moat/)

---

## The Margin (M3)

**Will this make money or bleed it?**

- **Gross Margin (current):** £1.66 PEPM (For all uiser types)
- **Gross Margin (AI-adjusted):** £250 PEPM (For admin only)
- **Pricing Model:** hybrid (seat-based)
- **Pricing Today → Tomorrow:** £1.66 PEPM → £250 PEPM
- **Total AI COGS / unit:**
- **Cascading Strategy:** Triage: GPT 4-0; frontier: Gemini; ratio 10:1
- **Net Margin Shift:** Net margin shift is significant for this user persona. Net impact as a whole is minimal, as Admins are a minority population.
- **Break-even at:**

→ Details: [`03-the-margin/`](03-the-margin/)

---

## The Contract (M4)

**Why users will trust a probabilistic system.**

- **Reliability Target:** ≥92% on the gold set at the MCP layer. ≥95% on the two auto-permitted action categories (data return, group operations) where there is no human gate.
- **Golden Dataset:** 5 rows, 3 adversarial
- **Confidence UX:** tiered confidence + human-in-loop trigger. The M5 autonomy policy sits above the tier (policy is the floor; tiers gate within an action category).
- **HITL Architecture:** The M5 autonomy policy is the floor. Confidence tiers gate within action categories; the policy gates across them.
- **Failure Mode Coverage:** *Suggested finding (plausible, partner-style; swap with real workshop feedback when you have it):*

→ Details: [`04-the-contract/`](04-the-contract/)

---

## The Guardrails (M5)

**What breaks when this scales — and what compounds.**

- **Compounding System:** | Loop | Input | Output | Compounds? | Status | |------|-------|--------|-----------|--------| | Recursive Learning | Production telemetry from Mixpanel: Model Context Protocol (MCP) tool-call success and failure, latenc…
- **Governance Posture:** Policy covers the scope of Artificial Intelligence (AI) assistance for administrators (the Kallidus LMS Admin Agent). Excludes AI use-cases for end-users (learners), which fall under a separate, future policy scope.
- **Autonomy Boundaries:** • Return of data for administrator - auto.
- **Escalation Triggers:** 1. Confidence in response <70%: stop the task and ask the admin for more information.
- **Audit Cadence:** • Daily - system-use metrics reviewed by PM (Mixpanel + Grafana dashboards).
- **Shadow AI Audit (user-side):** __ workarounds found · Target end-state, ~6-8 sanctioned tools. Triage priorities: build candidates · adjacent spend £8-15k per year unaccounted (individual subscriptions on personal cards or free tiers; opportunity cost of duplicated tooling). Small in absolute terms; matters because the *risk* exposure is disproportionate to the spend.
- **Agent Boundaries:** _Not shipping agents this version. The product is a Model Context Protocol (MCP) server orchestrated by the customer's choice of Large Language Model (LLM) client; we control the tools and gates, the customer's chosen LLM does the orchestra…
- **Regulatory Exposure:** • **General Data Protection Regulation (GDPR):** In scope. Risk tier: minimal. Controls: data return is limited to data the requesting admin already has scope to see in the underlying Kallidus permissions model.…

→ Details: [`05-the-guardrails/`](05-the-guardrails/)

---

## The Pitch (M6)

**How you get this funded, shipped, and adopted.**

- **Horizon 1 (Now):** Closed-beta of the Model Context Protocol (MCP) Admin Agent with 5-10 design-partner customers, on the existing Workato + Admin Application Programming Interface (API) stack · Reliability instrumentation live - the Module 4 (M4) contract running in production behind a feature flag
- **Horizon 2 (Next):** General Availability (GA) launch of the AI Admin seat at £250 PEPM, with the Module 5 (M5) autonomy policy and reliability contract live · Network Intelligence loop fix - opt-in cross-tenant anonymised gold-set pipeline (closes the M2 weakest flywheel input, 1/5)
- **Horizon 3 (Bet):** Unified workforce-platform orchestrator - one agent reasoning across the learning management, performance management, and talent management modules, executing multi-module workflows (e.g. correlating overdue compliance training with a manager's goal-setting cadence and proposing an integrated intervention)
- **Board Narrative:** The most defensible AI revenue in enterprise workforce software is the administrative layer, and a 12-month window exists to take it before Learning Experience Platform (LXP) attackers close the gap or big-tech platforms encroach.
- **Ask:** 1. **Strategic alignment - "are we in or out" on this bet.** A 12-month window does not survive a half-commitment. We are asking the board to commit explicitly to the thesis, not to defer to a stage-gate next quarter.
- **Key Strategic Change:**

→ Details: [`06-the-pitch/`](06-the-pitch/)
