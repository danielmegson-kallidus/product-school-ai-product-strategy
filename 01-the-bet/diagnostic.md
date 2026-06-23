# Three-Axis Vulnerability Diagnostic

## Product
LMS Admin Agent - Model Context Protocol (MCP) server orchestrated by the customer's choice of Large Language Model (LLM) client, exposing the admin surface of an enterprise Learning Management System (LMS).

**Product:** Learning Management System
**Your Role:** Lead Product Manager

---

## Scores

### Contextual Moat - 4/5
*Workflow depth × switching cost. Would users leave in a weekend if a competitor showed up?*

**Score rationale:** Multi-year contracts (3-5 year average term). Complex onboarding and offboarding (90+ days typical). Admin workflows are embedded across compliance, reporting, integrations, and HRIS data flows. B2B switching cost is operational, not just commercial - moving providers is a programme of work, not a procurement decision. Customer Effort Score on admin tasks is the moat; the agent makes that score better, not worse.

**Named attacker (from partner challenge):** Cornerstone OnDemand, Learning Pool, Thrive LXP. None has shipped an MCP-orchestrated admin surface at parity.

---

### Data Advantage - 3/5
*Proprietary signal that compounds with usage. What do you see that OpenAI doesn't?*

**Score rationale:** Cumulative customer telemetry (8+ years for the enterprise cohort) covers learner outcome data, admin task sequences, compliance assignment patterns, and integration-event traces. Newer entrants cannot reconstruct this signal. Score capped at 3/5 because today the data is per-tenant; the Network Intelligence loop fix (committed to Horizon 1 in M5) lifts this to 4/5 once cross-tenant anonymised signal is live.

**Named attacker (from partner challenge):** Cornerstone OnDemand, Learning Pool, SAP SuccessFactors, Thrive LXP.

---

### Platform Exposure - 2/5
*Encroachment risk × pivot speed. If Apple/Google/OpenAI ships your hero feature native - then what?*

**Score rationale:** The space is innovating quickly and the underlying technology stack is reproducible. A platform vendor (OpenAI, Google, Microsoft) could ship a generic admin agent within 12-18 months, but cannot replicate workflow-specific permissions, audit, and integration depth without rebuilding the underlying data model. Pivot speed is acceptable - model-agnostic architecture (M2 kill-switch is "Ready") means we can absorb a platform shift without rewriting the product.

**Named attacker (from partner challenge):** OpenAI (vertical agent stack), Microsoft (Copilot for Workforce), Google (Workspace agent surface).

---

## Top Vulnerability
Encroachment by vertical Learning Experience Platform (LXP) competitors targeting the Network Intelligence loop weakness (M2: 1/5 today, fix committed in H1). Faster commercial growth by these competitors is the proximate risk; the underlying cause is the cross-tenant learning gap.

## Confidence Level
M-H. Moved from M based on prototype validation (12 admin users, 5 design partners), completed reliability and governance design (M4 and M5), and a documented 12-month window before named attackers reach feature parity.
