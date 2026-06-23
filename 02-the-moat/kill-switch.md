# Kill Switch Audit

## Vendor Dependency Assessment

| Dimension | Current State | Risk Level | 48-Hour Action |
|-----------|--------------|------------|---------------|
| **Provider** | 2 active (Gemini frontier, GPT-4o triage); 3rd (Anthropic Claude) certified in test environment, available via cloud marketplace within 24 hours | L | Promote certified 3rd provider to production via configuration toggle; no code change required |
| **Abstraction** | Model-agnostic. All model calls routed through the MCP server's policy and schema layer; prompt templates are model-portable | L | Swap model behind the abstraction; no consumer-side change |
| **Routing** | Model-agnostic cascade routing (10:1 triage to frontier). Routing rule lives in the MCP server, not in the prompt | L | Re-tune cascade ratio per replacement model's cost / quality profile within 48 hours |
| **Eval** | Automated gold-set eval running weekly, with auto-rollback gated on hallucination ≥2% and accuracy <90% thresholds (M4 reliability contract). Owner: Product + Engineering on-call. Closed: H1 week 4 | L | Re-baseline against the new model in the eval pipeline; release gated on threshold pass |
| **Capability: cross-tenant anonymisation pipeline** | Build in flight, H1 deliverable. Owner: Data Engineering Lead. Dependencies: DPO sign-off, customer InfoSec review | M | Continue build to H1 close; pre-stage DPO review in week 6 of H1 |
| **Capability: prompt-template versioning and rollback** | Live in production behind feature flag. Owner: ML Engineering. Last-known-good restore tested fortnightly | L | Trigger rollback via existing runbook; <15 minute recovery |
| **Capability: MLOps observability (per-model accuracy, drift, hallucination tracked separately)** | Live. Datadog + Grafana dashboards. Owner: Engineering on-call | L | Continue monitoring; alert thresholds tuned per the M4 contract |

## Portability Score
Ready. Three providers certified, one swap rehearsed in test, no contractual lock-in to any single vendor.

## If [primary vendor] doubles pricing tomorrow:
Swap to the certified secondary provider via configuration toggle within 48 hours. Re-tune cascade ratio to defend margin (M3 stress test confirms ~70% gross margin survives a 50% vendor price hike at current ratio; doubling absorbed by cascade re-tuning).

## If [primary vendor] ships a competing product:
The competing product would sit at the LLM-client layer, not at the MCP server layer. Our moat sits in the tool surface, the autonomy policy, the permissions model, and the multi-year admin workflow embedment - none of which transfers to a vendor-hosted agent. Defence: accelerate the unified workforce-orchestrator (Horizon 3 bet) so the agent's value lives in cross-module reasoning the vendor cannot reach. B2B switching cost holds the existing book through the transition window.
