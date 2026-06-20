# RI OS — Multi-Agent Revenue Intelligence Platform

**A governed, deterministic, auditable, multi-tenant operating system for turning fragmented account, market, payment, and workflow data into auditable revenue decisions in regulated environments.**

[View Live Architecture (Notion)](https://beautiful-relative-aef.notion.site/RI-OS-38563b107cf380289821d7336f9a347e)

---

## Overview

RI OS is a portfolio-grade reference architecture for a Senior Revenue Intelligence / RevOps leadership context. The architecture is modeled for a national licensing organization operating across jurisdictions, unifying four intelligence layers on a single Customer 360 spine with deterministic classification, auditable signals, and RACI-governed workflows throughout.

## Core Architecture Principles

| Principle | Description |
|-----------|-------------|
| Governance-first | RACI and change control are load-bearing architecture |
| Signal bus over direct coupling | Agents write to shared tables, not each other |
| Configuration over code | Reference tables drive behavior; no hardcoded logic |
| Jurisdiction-aware data hierarchy | Statistics Canada > ISED > BDC > provincial > US Census |
| Bottom-up primary for TAM | Establishment math is the anchor |

## The Five Intelligence Layers

### Layer A — Lead Intelligence Engine (Phase 1)
**Question:** Who should be in our world that isn't yet?

- External signal scanning: Google Maps enrichment, provincial regulatory database ingestion
- 3-layer matching engine (exact -> fuzzy -> geo-radius)
- Closed business audit, net-new lead discovery with scoring and tiering
- Live TAM capture rate computation
- **Produces:** 5 signals | **Consumes:** 2

### Layer B — Classification Engine (Phase 2)
**Question:** Which accounts are at risk, growing, or leaking — and why?

- Deterministic classification: Whale/Core/Long Tail value tiers
- Payment behaviour: Delinquent/Deteriorating/Stable/Healthy
- 8 strategic action tags (Tag 0 EXTERNAL CLOSURE FORCE through Tag 7 MAINTAIN)
- Strict priority ordering, confidence scoring, SLA-driven routing
- **Produces:** 3 signals | **Consumes:** 4

### Layer C — Cash Intelligence Engine (Phase 3)
**Question:** Where is cash sitting, how long, and what is the trend?

- Payment conversion matrices by method/segment/month
- Rolling DSO with 6/12-month trends
- 7-type anomaly detection with configurable thresholds
- Persistent anomaly escalation, priority account sensitivity
- Payment method migration tracking
- **Produces:** 3 signals | **Consumes:** 2

### Layer D — TAM Analyst (On-demand)
**Question:** How big is our market and how much have we captured?

- Bottom-up primary TAM methodology with top-down triangulation
- NAICS mapping with de-duplication, sales capacity SOM
- Red team challenge, defensibility scoring (A-F)
- Investor-readiness quality gate
- **Produces:** 1 signal | **Consumes:** 2

### Layer E — Insight Narrative Engine (Phase 4)
**Question:** What should each audience do, and when?

- Synthesis layer that merges all 4 agent outputs into plain-English, audience-adaptive insight cards
- Detects 8 multi-signal patterns: DECLINING_BUSINESS, HIDDEN_GROWTH, SILENT_CHURN, CONFIRMED_LOSS, PAYMENT_METHOD_REGRESSION, PORTFOLIO_CONCENTRATION_RISK, MARKET_PENETRATION_OPPORTUNITY, IMPROVING_PORTFOLIO
- Produces narratives for Executive, AM, Collections, BD, and Ops
- Every fact audited against source data
- Degrades gracefully from FULL (4 agents) to BASIC (Classification only)
- **Produces:** 8 narrative patterns | **Consumes:** 4

## Platform Diagram

```
[Lead Engine] --> [Classification Engine] --> [Cash Engine] --> [Narrative Engine]
     |                   |                        |                   |
     v                   v                        v                   v
[Customer 360 Spine + Signal Bus (append-only, auditable)]
     |
     v
[Dashboards/UI]    [Outbound Integration (Slack/RevOps)]
```

## Data Pipeline

```
Ingest (ERP, CRM, Maps, Provincial Registers) -> Extract -> Stage -> Validate -> Transform -> Load -> Signal Bus -> Agents -> Narrative -> Dashboards
```

## RACI Governance

| Role | Executive Sponsor | RevOps/CRM Owner | IT/Data | Finance | Collections | Sales/BD/AM | Ops |
|------|-------------------|------------------|---------|---------|-------------|-------------|-----|
| Lead Engine | A | R | C | I | I | I | I |
| Classification | A | R | C | I | I | C | C |
| Cash Engine | A | R | C | C | R | I | I |
| TAM Analyst | R | C | I | C | I | C | I |
| Narrative Engine | R | C | I | C | C | C | C |

*R = Responsible | A = Accountable | C = Consulted | I = Informed*

## NDA Note

This repository contains no client identifiers, proprietary data, or confidential information. All examples use placeholder names. The architecture is a reference design, not an implementation of any specific client system.

## License

MIT License - portfolio reference material

---

Created by Artem Pr. | Built with AI-assisted architecture design
