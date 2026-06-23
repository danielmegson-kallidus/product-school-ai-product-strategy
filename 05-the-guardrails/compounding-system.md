# Compounding System Design

## Feedback Loops

| Loop | Input | Output | Compounds? | Status |
|------|-------|--------|-----------|--------|
| Recursive Learning | Production telemetry from Mixpanel: Model Context Protocol (MCP) tool-call success and failure, latency, retries, abandonment, session length | Weekly gold-set additions, MCP tool-schema fixes, prompt-template updates, latency budgets revised | Y | active |
| Cross-Domain Transfer | Admin corrections and complaints captured via Intercom, plus in-app override actions on agent outputs and Customer Success-relayed qualitative signals | New gold-set rows, MCP tool-description fixes, Help Centre documentation gaps closed, customer-facing release-note inputs | Y | active |
| Network Intelligence | Cross-tenant behaviour patterns: anonymised tool-call sequences, shared failure modes, regression signals across the customer base | Cross-tenant gold-set rows, early-warning detection of model drift before it lands at a second customer, shared schema improvements | N | missing |

**Broken loop identified by partner:** Network Intelligence (the same loop the partner flagged in Module 2 (M2) - it appears here as a missing flywheel input, in M2 as the weakest Data Flywheel score (1/5), and in M4 as a coverage gap in the gold set).

**Fix plan:** Build an opt-in anonymisation pipeline for tool-call sequences and outcomes. Opt-in by default for new tenants, opt-out toggle exposed in tenant admin settings for existing customers. Feeds a cross-tenant slice of the gold set so a regression observed at one customer surfaces a test row for everyone, and so the Recursive Learning loop has a network-scale signal to compound against. Add a traceable identifier on learning-completion events as the first concrete instrumentation step, since completion is the highest-signal outcome event and the easiest to anonymise.

## Context Connectivity

**How knowledge flows:**
• **Quantitative product signal** flows from the MCP server and Workato traces into Mixpanel (event telemetry) and Grafana (operational metrics, model performance dashboards). Picked up weekly by Product and continuously by Engineering on-call.
• **Qualitative admin signal** flows through Intercom (in-product chat and corrections), Customer Success and Customer Experience Manager (CEM) call notes, and Product Satisfaction (PSAT) surveys. Picked up by Product Managers (PMs) during weekly review, plus ad-hoc by Customer Success.
• **Cross-team synthesis** happens in the weekly Product + Engineering triage, which translates signals into (a) gold-set additions, (b) MCP and prompt fixes, (c) Help Centre documentation updates, and (d) release notes. The gold set is intended to be the connective artefact across all four loops.

**Where it silos:**
• **Tool-level silos:** Mixpanel (PMs see it, Support rarely does), Intercom (Support lives here, PMs visit it), Grafana (Engineering owns it, Product doesn't habitually open it). Each tool's audience is comfortable in their tool, which is precisely why signals don't cross-pollinate.
• **Role-level silos:** Customer Success holds high-context qualitative signal from customer calls that rarely makes it into the product backlog in structured form. Engineering eval results don't always loop back to PMs writing prompt updates. Sales-facing teams (Airfocus) see commercial signal that doesn't always meet model performance signal.
• **Tenant-level silos:** Today, every customer is an island for learning purposes (the M2 Network loop gap restated). A regression at Customer A teaches us nothing about Customer B until we hit it there too.
• **Fix:** Make the gold set the explicit single source of truth for "what we learned this week". Every silo writes to it; every release reads from it. Pair with the Network Intelligence loop fix above so the gold set also crosses the tenant boundary.

## Governance Policy

**Scope:** Policy covers the scope of Artificial Intelligence (AI) assistance for administrators (the Kallidus LMS Admin Agent). Excludes AI use-cases for end-users (learners), which fall under a separate, future policy scope.

**Autonomy boundaries:**
• Return of data for administrator - auto.
• Creation of groups - auto.
• Assignment of learning - human approval required.
• Deletion of users - never auto.

**Escalation triggers:**
1. Confidence in response <70%: stop the task and ask the admin for more information.
2. Error or cancel rate +10% above baseline within a 24-hour window: pause new sessions for the affected tenant pending triage.

**Audit cadence:**
• Daily - system-use metrics reviewed by PM (Mixpanel + Grafana dashboards).
• Real-time - response-level guardrails enforced in the response flow itself by Technology (MCP server schema validation, tool-call policy gates, prompt-injection detection).
• Weekly - Product + Engineering triage of corrections and overrides, feeding the gold set.

**Regulatory exposure (European Union (EU) Artificial Intelligence (AI) Act / other):**
• **General Data Protection Regulation (GDPR):** In scope. Risk tier: minimal. Controls: data return is limited to data the requesting admin already has scope to see in the underlying Kallidus permissions model. The MCP server enforces this at the tool layer, not the prompt layer.
• **EU AI Act:** Likely classification is *limited risk* (administrative productivity assistant, no automated decisions about people's rights or employment outcomes). Transparency obligations are met by exposing the tool-call trace ("the why") on every response. We will re-classify if the agent ever moves into decisions affecting individual learners (e.g. automated compliance-failure consequences).
• **Customer-side data residency:** EU customer data stays in EU-hosted infrastructure throughout the Workato + MCP + model-vendor path. Vendor choice constrained accordingly (Gemini and GPT-4o EU endpoints).

## Agent Topology

_Not shipping agents this version. The product is a Model Context Protocol (MCP) server orchestrated by the customer's choice of Large Language Model (LLM) client; we control the tools and gates, the customer's chosen LLM does the orchestration. This section therefore covers Shadow AI inventory across Kallidus internally and a flag on customer-side exposure._

**Total tools found:** ⚠️ Formal audit not yet run. Initial scan suggests:
• Sanctioned and in-use: Anthropic Claude (Product, Engineering, several other functions), GitHub Copilot or equivalent (Engineering), Gemini and GPT-4o (in-product, via Workato), Workato (iPaaS).
• Likely unsanctioned and in informal use: free-tier ChatGPT, Notion AI, Grammarly, various meeting-summary tools (Otter, Fathom, Read.ai), individual browser extensions.
• Estimated total surface: 12-18 tools across the company, of which 4-6 are formally sanctioned and the remainder need triage.

**Tools after triage:** Target end-state, ~6-8 sanctioned tools. Triage priorities:
1. Tools touching customer data (any meeting tool sitting in customer calls, any summariser ingesting tickets). Highest risk, fastest triage.
2. Tools touching code or product Intellectual Property (IP) (Copilot-like assistants, browser extensions with repo access).
3. Tools touching personal productivity only (low risk, can be sanctioned in bulk under an Acceptable Use Policy).

**Estimated hidden spend:** £8-15k per year unaccounted (individual subscriptions on personal cards or free tiers; opportunity cost of duplicated tooling). Small in absolute terms; matters because the *risk* exposure is disproportionate to the spend.
