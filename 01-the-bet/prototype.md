# The Prototype Bet

## What I Built
Prototype of a chat-based agentic experience using an iPaaS layer and the existing Admin API. Tested with 12 admin users across 5 design-partner customers (3 enterprise, 2 mid-market) over a 4-week sprint, covering 18 representative admin tasks (compliance reporting, cohort/group creation, course assignment drafting, user-data lookup).

## Tool Used
iPaaS-hosted Model Context Protocol (MCP) server, orchestrated by the customer's choice of Large Language Model (LLM) client (Claude, ChatGPT, Gemini).

## Prototype Link
(https://app.eu.workato.com/?fid=smart-mcp_server)

## AI Value Archetype
Orchestrator (Agentic). The product orchestrates deterministic admin tools via MCP; the customer's LLM client provides the natural-language surface and reasoning.

## The Bet in One Sentence
If we ship an MCP-based agentic admin experience, design-partner administrators will complete a defined basket of recurring admin tasks ≥50% faster, at ≥92% accuracy on the gold set, with ≥60% stating intent to convert to a paid AI Admin seat at £250 Per Employee Per Month (PEPM) by end of Horizon 1 (H1).

## Kill Criteria
1. **Adoption kill:** <40% of design-partner admins complete ≥3 sessions in any 2-week window during the 12-week beta. Decision date: end of week 12 of H1.
2. **Reliability kill:** Gold-set accuracy stays <85% (against the ≥92% target) for 4 consecutive weekly runs, OR hallucination rate sits >2% over any rolling 7-day window with no improving trend across two release cycles. Decision date: end of H1.
3. **Commercial kill:** <2 of the 5 design partners sign a Letter of Intent (LOI) at £250 PEPM by end of H1, AND blended willingness-to-pay across the design-partner cohort lands below £150 PEPM. Decision date: end of H1.
