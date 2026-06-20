# Classification Engine

The Classification Engine answers: **Which accounts are at risk, growing, leaking, or stable, and why?**

It applies deterministic rules to normalized account, payment, market, and signal data. The goal is not to predict vaguely; it is to produce explainable action tags with confidence, priority, and operational routing.

## Inputs

- Account profile and segment fields.
- Invoice and payment behavior.
- External signals from Lead Intelligence.
- Cash signals from Cash Intelligence.
- Tenant-specific license matrix, thresholds, and SLA configuration.

## Deterministic Classification

The engine assigns each account to value and health categories:

- Value tier: Whale, Core, Long Tail.
- Payment behavior: Delinquent, Deteriorating, Stable, Healthy.
- Strategic action tag: Tag 0 through Tag 7.

The strategic tags are evaluated in strict priority order so the same input state always produces the same output.

## Strategic Action Tags

| Tag | Public Description |
| --- | --- |
| Tag 0 | External closure force |
| Tag 1 | High-value account at risk |
| Tag 2 | Payment deterioration |
| Tag 3 | Hidden growth opportunity |
| Tag 4 | Coverage or license gap |
| Tag 5 | Portfolio monitoring |
| Tag 6 | Stable account |
| Tag 7 | Maintain |

## Outputs

Classification publishes:

- `CLASSIFICATION_RESULT`
- `HIGH_VALUE_AT_RISK`
- `PORTFOLIO_HEALTH_SNAPSHOT`

Each output includes:

- Assigned tag.
- Confidence score.
- Rule version.
- Source signal references.
- Recommended owner or queue.

## Governance Requirements

- Rules are versioned and auditable.
- Threshold changes require approval.
- Classification runs are reproducible.
- Role-based access controls determine who can see account-level details.

## Portfolio Value

This layer demonstrates RevOps operating rigor: clear prioritization, transparent rules, and accountable routing instead of one-off reporting.

