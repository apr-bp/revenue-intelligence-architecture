# Signal Bus

The signal bus is the coordination layer for the architecture. Agents publish signals to the bus; downstream layers consume them by contract. Agents do not call each other directly.

## Contract Shape

Each signal includes:

- `signal_id`
- `tenant_id`
- `run_id`
- `signal_type`
- `source_layer`
- `target_layer`
- `severity`
- `confidence_score`
- `payload`
- `rule_version`
- `created_at`
- `expires_at`

## Reference Signal Types

| Signal | Source | Target | Purpose |
| --- | --- | --- | --- |
| `EXTERNAL_CLOSURE` | Lead Intelligence | Classification | External source suggests an account may no longer be active |
| `EXTERNAL_DISTRESS` | Lead Intelligence | Classification | External source suggests business risk |
| `LICENSE_GAP_DETECTED` | Lead Intelligence | Classification | Market coverage or licensing gap detected |
| `AR_AT_RISK` | Lead Intelligence | Cash Intelligence | Market signal may affect receivables risk |
| `CAPTURE_RATE_UPDATE` | Lead Intelligence | TAM Analyst | Addressable-market coverage changed |
| `CLASSIFICATION_RESULT` | Classification | Lead Intelligence | Classification result available for enrichment logic |
| `HIGH_VALUE_AT_RISK` | Classification | Cash Intelligence | Priority account needs cash-risk sensitivity |
| `PORTFOLIO_HEALTH_SNAPSHOT` | Classification | Dashboard | Portfolio health summary available |
| `PAYMENT_ANOMALY` | Cash Intelligence | Classification | Payment behavior anomaly detected |
| `SEGMENT_PAYMENT_BENCHMARK` | Cash Intelligence | Lead Intelligence | Segment-level payment benchmark available |
| `CASH_HEALTH_SNAPSHOT` | Cash Intelligence | Dashboard | Cash-health summary available |
| `TAM_STUDY_PUBLISHED` | TAM Analyst | Dashboard | Market-sizing study available |

## Why This Pattern Matters

- It avoids circular dependencies.
- It allows each layer to be tested independently.
- It creates a complete audit trail.
- It supports graceful degradation when one layer is unavailable.
- It makes multi-tenant behavior configurable rather than hardcoded.

