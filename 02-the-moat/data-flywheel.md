# Data Flywheel Map

> Score each loop 1-5. Your weakest loop is where competitors attack first.
> The four loops below are the M2 starting point - adapt if your product has 2 or 6 loops instead of 4.

## Flywheel Loops

| Loop | What It Measures | Score 1 | Score 5 | Score |
|------|------------------|---------|---------|-------|
| **Correction** | Do users fix AI outputs? Is that signal captured and reused? | No capture | Automated retraining | 4/5 |
| **Preference** | Does the product learn individual / team preferences over time? | Stateless | Deep personalization | 3/5 |
| **Domain Context** | Does usage in one area improve quality in adjacent areas? | Siloed | Cross-domain transfer | 4/5 |
| **Network** | Does each new user / team make the product better for everyone? | Isolated | Strong network effects | 4/5 |

### Correction Loop - 4/5
**What you capture today:** Every admin correction or override is logged with the original input, the tool-call trace, the model output, and the corrected output. Routed via Mixpanel and Intercom into a weekly Product + Engineering triage. Becomes (a) new gold-set rows, (b) MCP schema or tool-description fixes, (c) prompt-template fixes.
**How it compounds:** Corrections feed the gold set; the gold set is the regression suite; each release is held against it. Recursive Learning loop runs weekly, owned by Product + Engineering on-call.

### Preference Loop - 3/5
**What you capture today:** Per-admin defaults (preferred report grain, default cohort filters, common group templates) are persisted at the tenant level. Cross-admin preference inference is not yet active.
**How it compounds:** Defaults reduce session length on recurring tasks; recurring-task patterns become candidate templates surfaced to the broader admin pool within the tenant. H2 build extends inference across the tenant; full cross-tenant preference learning is gated on the Network loop pipeline.

### Domain Context Loop - 4/5
**What you capture today:** Admin task patterns in compliance reporting carry context into related areas (group composition, assignment drafting, audit-trail navigation). Tool-call sequences are captured and the graph of co-used tools informs MCP tool-description tuning.
**How it compounds:** A high-quality compliance-report run improves the next group-creation suggestion in the same session; cross-tool patterns inform tool-description revisions, which lift accuracy on adjacent tools at the next release.

### Network Loop - 4/5
**What you capture today (post-H1 commitment):** Opt-in anonymised cross-tenant tool-call sequences, shared failure modes, and regression signals across the customer base. Pipeline committed as an H1 deliverable (was H2; pulled forward to close the strategy's largest single risk). Anonymisation reviewed by Data Protection Officer (DPO) and customer Information Security teams before any tenant is enrolled. Today (pre-pipeline): 1/5. Target by end of H1: 4/5.
**How it compounds:** A misbehaving pattern at one customer surfaces a test row for everyone within the same release cycle. Regression lead-time improves by an expected ≥14 days. Cumulative cross-tenant gold-set rows compound the Correction loop above.

**Total Flywheel Score: 15/20 (post-H1 commitment); 8/20 today**
**Weakest Loop:** Preference (3/5 post-H1; cross-tenant preference inference gated on the Network pipeline)
**Fix for weakest loop:** Phase 1 (H1): tenant-level preference defaults shipped alongside the Network pipeline. Phase 2 (H2): cross-tenant preference inference, opt-in, leveraging the same anonymisation layer.

---

## Encroachment Threat Assessment

### 1. Platform Encroachment
**Attacker:** Thrive LXP
**Vector:** Building toward an MCP-orchestrated admin surface; currently announced, not shipped. Strong AI / data narrative, shallower workflow depth.
**Time-to-threat:** 12 months to feature announcement, 18 months to enterprise-credible parity.
**% of value at risk:** 10% of admin-segment Annual Recurring Revenue (ARR) if they ship at parity by month 12; 5% if they miss the window.

### 2. Vertical Competitor
**Attacker:** Learning Pool
**Vector:** Expansion into our vertical via partnership with a platform LLM provider. Likely white-labelled agent surface rather than first-party.
**Time-to-threat:** 12 months to commercial pilot, 24 months to displacement risk.
**% of value at risk:** 5% of admin-segment ARR over 24 months.

### 3. Adjacent Expansion
**Attacker:** Thrive LXP
**Vector:** Adjacency play - moving from learner-experience into admin productivity, positioning AI Admin as part of a unified workforce-experience layer.
**Time-to-threat:** 12 months.
**% of value at risk:** 10% of admin-segment ARR, with secondary risk to learner-side renewals if positioning lands.

---

## 90-Day Encroachment Plan

*Your partner played the Big Tech attacker. What was their plan to kill you?*

**Attacker:** Thrive LXP
**Attack vector (target the weakest loop):** Network loop - position a unified cross-tenant data model as a structural advantage over our per-tenant approach.
**Weeks 1-4 - what they ship:** Marketing-led launch of a unified data model for their agent. Demo-quality, not production-grade.
**Weeks 5-8 - how they poach users:** Cold outreach to our top 20 admin-segment accounts via shared Customer Success contacts and named-account sales motion. Conference presence at the major industry event.
**Weeks 9-12 - why users don't come back:** Sales approach is strong; product cannot deliver against the demo. Admin-segment switching cost (multi-year contracts, complex on/offboarding) holds. Customers who run a parallel pilot return citing reliability and integration depth.
**Your defense:**
1. Pull the Network Intelligence pipeline into H1 (committed in M5). Closes the structural weakness before the attacker can use it as a narrative.
2. Publish the reliability contract (M4) externally as a customer-facing artefact. Reliability is itself a competitive moat - it lets enterprise buyers say yes.
3. Convert ≥3 of the top 5 design partners to LOI at the H1 gate, locking in commercial momentum before any attacker can offer parallel terms.
