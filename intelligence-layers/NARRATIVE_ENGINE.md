# Narrative Engine

The Narrative Engine answers: **What should each audience understand, trust, and do next?**

It synthesizes outputs from the intelligence layers into plain-language insight cards for executive, account management, collections, business development, and operations audiences.

## Inputs

- Latest completed classification results.
- Cash-health and anomaly signals.
- Lead intelligence and market-gap signals.
- Portfolio-level health snapshots.
- Role and audience configuration.

## Pattern Detection

The engine detects eight multi-signal patterns:

- `DECLINING_BUSINESS`
- `HIDDEN_GROWTH`
- `SILENT_CHURN`
- `CONFIRMED_LOSS`
- `PAYMENT_METHOD_REGRESSION`
- `PORTFOLIO_CONCENTRATION_RISK`
- `MARKET_PENETRATION_OPPORTUNITY`
- `IMPROVING_PORTFOLIO`

## Narrative Controls

Every narrative must include:

- Source signal references.
- Confidence level.
- Audience type.
- Suggested action.
- Suppressed details when the viewer lacks permission.

Every factual claim must trace back to a source field, rule result, or signal payload.

## Graceful Degradation

Narratives degrade by data availability:

- Full mode: all intelligence layers available.
- Partial mode: one or more supporting layers unavailable.
- Basic mode: classification only.

## Portfolio Value

This layer demonstrates executive communication design: complex revenue operations signals converted into concise, auditable, role-specific decisions.

