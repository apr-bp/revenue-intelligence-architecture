# Cash Intelligence

Cash Intelligence answers: **Where is cash sitting, how long has it been there, and what is changing?**

It transforms invoices and payments into operational cash-health signals. The emphasis is on trend detection, anomaly escalation, and the relationship between payment behavior and account priority.

## Inputs

- Generic invoice records.
- Generic payment records.
- Account value tier and segment.
- Classification outputs.
- Tenant-specific aging, DSO, and anomaly thresholds.

## Core Measures

- Rolling DSO.
- Payment conversion rate by method, segment, and period.
- Aging distribution.
- Payment method migration.
- Priority-account exposure.
- Run-over-run cash-health movement.

## Anomaly Types

The reference design supports seven anomaly categories:

1. Sudden DSO increase.
2. Payment method regression.
3. High-value unpaid exposure.
4. Segment-level payment deterioration.
5. Repeated late payment pattern.
6. Unusual payment timing.
7. Persistent unresolved anomaly.

## Outputs

Cash Intelligence publishes:

- `PAYMENT_ANOMALY`
- `SEGMENT_PAYMENT_BENCHMARK`
- `CASH_HEALTH_SNAPSHOT`

## Governance Requirements

- Financial formulas are documented and versioned.
- Currency and exchange-rate assumptions are explicit.
- Anomaly thresholds are configurable by tenant.
- Sensitive account-level financial details are role-restricted.

## Portfolio Value

This layer demonstrates how finance, collections, and RevOps can share one auditable view of cash risk without exposing raw financial records in public documentation.

