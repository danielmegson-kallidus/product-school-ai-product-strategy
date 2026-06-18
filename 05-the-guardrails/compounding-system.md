# Compounding System Design

## Feedback Loops

| Loop | Input | Output | Compounds? | Status |
|------|-------|--------|-----------|--------|
| | | | Y/N | active / broken / missing |
| | | | Y/N | active / broken / missing |
| | | | Y/N | active / broken / missing |

**Broken loop identified by partner:**
**Fix plan:**

## Context Connectivity
<!-- How does knowledge flow across teams and domains? Where does it silo? -->
## Feedback Loops

| Loop | Input | Output | Compounds? | Status |
|------|-------|--------|-----------|--------|
| Recursive Learning | Mixpanel data | Update golden dataset | Y | active |
| Cross-Domain Transfer | User corrections in intercom | Update golden dataset | Y | active |
| Network Intelligence | Usage volume data | Update golden dataset | N | missing |

**Broken loop identified by partner:** Network Intelligence
**Fix plan:** Add a traceable action for Learning completion

## Context Connectivity
<!-- How does knowledge flow across teams and domains? Where does it silo? -->

**How knowledge flows:** PSAT signals, Feedback, Usage data

**Where it silos:** Mixpanel, Intercom, Grafana

## Governance Policy

**Scope:** Policy covers scope of AI assistance for administrators Excludes: AI use-cases for end-users

**Autonomy boundaries:** Return of data for administrator — auto. Creation of groups — auto. Assignment of learning — human approval required. Deletion of users — never auto.

**Escalation triggers:** (1) Confidence in response < 70% - stop task and ask for more info (2) Error/cancel rate +10%

**Audit cadence:** Daily — System use metrics (PM). Real-time — Within response flow (Technology).

**Regulatory exposure (EU AI Act / other):** GDPR. Risk tier: minimal. Controls: Data return is limited to data in scope for user already.

## Agent Topology

_Not shipping agents this version._

**Total tools found:**
**Tools after triage:**
**Estimated hidden spend:**
