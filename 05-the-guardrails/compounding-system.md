# Compounding System Design

## Feedback Loops

| Loop | Input | Output | Compounds? | Status |
|------|-------|--------|-----------|--------|
| Recursive Learning | Production telemetry from Mixpanel: Model Context Protocol (MCP) tool-call success and failure, latency, retries, abandonment, session length | Weekly gold-set additions, MCP tool-schema fixes, prompt-template updates, latency budgets revised | Y | active |
| Cross-Domain Transfer | Admin corrections and complaints captured via Intercom, plus in-app override actions on agent outputs and Customer Success-relayed qualitative signals | New gold-set rows, MCP tool-description fixes, Help Centre documentation gaps closed, customer-facing release-note inputs | Y | active |
| Network Intelligence | Opt-in anonymised cross-tenant tool-call sequences, shared failure modes, regression signals across the customer base. Pipeline live as an H1 deliverable (pulled forward from H2). | Cross-tenant gold-set rows (~30% of new additions), early-warning detection of model drift before it lands at a second customer, shared schema improvements, regression lead-time improved by ≥14 days | Y | active (H1) |
| Preference Inference | Per-tenant defaults and recurring-task patterns from session telemetry | Tenant-level default surfaces; H2 extends to cross-tenant preference inference via the Network pipeline | Y | partial - tenant live, cross-tenant H2 |

**Previously broken loop (now closed):** Network Intelligence. Was scored 1/5 in M2 and "missing" here. Pipeline build pulled into H1 as the single highest-leverage strategy investment, since the same loop appeared as a gap in M2 (data flywheel), M4 (gold-set coverage), and M5 (compounding system). One fix closes three gaps.

**Build summary:** Opt-in anonymisation pipeline for tool-call sequences and outcomes. Opt-in by default for new tenants, explicit opt-in for existing customers via tenant admin settings. Feeds a cross-tenant slice of the gold set so a regression observed at one customer surfaces a test row for everyone. Anonymisation reviewed and signed off by the Data Protection Officer (DPO) and customer Information Security (InfoSec) teams. Owner: Data Engineering Lead, with PM oversight on the gold-set integration.

## Context Connectivity

**How knowledge flows:**
• **Quantitative product signal** flows from the MCP server and iPaaS traces into Mixpanel (event telemetry) and Grafana (operational metrics, model performance dashboards). Picked up weekly by Product and continuously by Engineering on-call.
• **Qualitative admin signal** flows through Intercom (in-product chat and corrections), Customer Success and Customer Experience Manager call notes, and Product Satisfaction (PSAT) surveys. Picked up by Product Managers during weekly review, plus ad-hoc by Customer Success.
• **Cross-team synthesis** happens in the weekly Product + Engineering triage, which translates signals into (a) gold-set additions, (b) MCP and prompt fixes, (c) Help Centre documentation updates, and (d) release notes. The gold set is the explicit single source of truth across all four loops.
• **Cross-tenant signal** flows through the H1 anonymisation pipeline into the same triage, with cross-tenant rows tagged so they can be reviewed for tenant-specific edge cases before merge.

**Where it silos (and how we close it):**
• **Tool-level silos:** Mixpanel (Product), Intercom (Support), Grafana (Engineering) each had a primary audience. Closed via: a unified weekly triage that pulls from all three; shared dashboards in a Product-Engineering channel; gold-set as the artefact-of-record.
• **Role-level silos:** Customer Success qualitative signal previously bypassed the product backlog. Closed via: structured weekly Customer Success input into the triage, mapped to gold-set candidate rows; Engineering eval results circulated back to PMs ahead of prompt updates; commercial signal (Airfocus) sits alongside model performance signal in the triage agenda.
• **Tenant-level silos:** Previously every customer was an island for learning purposes. Closed via the H1 Network Intelligence pipeline.

## Governance Policy

**Scope:** Policy covers Artificial Intelligence (AI) assistance for administrators (the LMS Admin Agent). Excludes AI use cases for end users (learners), which fall under a separate, future policy scope.

**Autonomy boundaries:**
• Return of data for administrator - auto (confidence-gated).
• Creation of groups and group membership - auto (confidence-gated, sequence-aware per the M4 red-team fix).
• Assignment of learning - human approval required, regardless of confidence.
• Deletion of users - never auto. No MCP tool exposed to the orchestrator.

**Escalation triggers:**
1. Confidence in response <70%: stop the task and ask the admin for more information.
2. Error or cancel rate +10% above baseline within a 24-hour window: pause new sessions for the affected tenant pending triage.
3. Hallucination rate ≥2% in any 24-hour window: auto-rollback to last-known-good MCP schema and prompt-template version, page on-call (per M4 contract).
4. Tool-chain composition pattern matching a known approval-gate-bypass signature: block at the MCP layer, log to security review.

**Audit cadence:**
• Real-time - response-level guardrails enforced in the response flow itself by Engineering (MCP server schema validation, tool-call policy gates, prompt-injection detection, sequence-aware policy gating).
• Daily - system-use metrics reviewed by PM (Mixpanel + Grafana dashboards).
• Weekly - Product + Engineering triage of corrections and overrides, feeding the gold set.
• Quarterly - external audit-ready report covering reliability contract performance, governance policy adherence, and regulatory exposure status.

**Regulatory exposure (European Union (EU) Artificial Intelligence (AI) Act / other):**
• **General Data Protection Regulation (GDPR):** In scope. Risk tier: minimal. Controls: data return is limited to data the requesting admin already has scope to see in the underlying permissions model. The MCP server enforces this at the tool layer, not the prompt layer. Data Protection Impact Assessment (DPIA) completed and signed off by the DPO at H1 week 4.
• **EU AI Act:** Classification is *limited risk* (administrative productivity assistant, no automated decisions about people's rights or employment outcomes). Transparency obligations met by exposing the tool-call trace ("the why") on every response. Re-classification triggered if the agent ever moves into decisions affecting individual learners.
• **Customer-side data residency:** EU customer data stays in EU-hosted infrastructure throughout the iPaaS + MCP + model-vendor path. Vendor choice constrained accordingly (Gemini and GPT-4o EU endpoints, Anthropic Claude EU endpoint certified for failover).

## Agent Topology

_Not shipping agents this version. The product is an MCP server orchestrated by the customer's choice of LLM client; we control the tools and gates, the customer's chosen LLM does the orchestration. This section therefore covers Shadow AI inventory across the organisation internally and a flag on customer-side exposure._

**Total tools found (audit completed, H1 week 6):** 17 distinct AI tools in use across the organisation.

**Sanctioned and in active use (6):**
• Anthropic Claude (Product, Engineering, multiple other functions)
• GitHub Copilot (Engineering)
• Gemini (in-product, via iPaaS)
• GPT-4o (in-product, via iPaaS)
• iPaaS platform itself (orchestration)
• A meeting-summary tool, vendor-of-record contract, deployed across Customer Success and Sales calls with customer-side opt-in

**Unsanctioned and active at audit close (11, of which 11 triaged):**
• Free-tier ChatGPT (4 functions)
• Notion AI (2 functions)
• Grammarly (3 functions)
• Two further meeting-summary tools (Customer Success, Sales)
• Various individual browser extensions (5+ instances, mostly Engineering and Product)

**Tools after triage:** Target end-state 7 sanctioned tools. Triage outcomes:
1. Tools touching customer data - migrated to the sanctioned meeting tool by end of H1 week 8; unsanctioned alternatives removed under the Acceptable Use Policy (AUP).
2. Tools touching code or product Intellectual Property (IP) - GitHub Copilot remains sanctioned; ad-hoc browser extensions with repo access removed.
3. Tools touching personal productivity only - Grammarly added to sanctioned list under enterprise terms; free-tier ChatGPT and Notion AI consolidated to the sanctioned Anthropic Claude estate.

**Workarounds found:** 11. **Workarounds remediated by end of H1:** 11. **Net Shadow AI surface post-triage:** 0 unsanctioned tools in active use.

**Estimated hidden spend:** £8-15k per year unaccounted (individual subscriptions on personal cards or free tiers; opportunity cost of duplicated tooling). Small in absolute terms; matters because the *risk* exposure is disproportionate to the spend. Post-triage: hidden spend zero, consolidated spend ~£22k per year on the sanctioned 7-tool estate, net of unsanctioned-tool sunset.

**Customer-side AI exposure:** Customers' choice of LLM client (the surface the MCP server is exposed to) is captured at tenant configuration and reviewed quarterly. Tenants are required to attest to their LLM-client vendor's data-processing terms as a precondition of agent enablement.
