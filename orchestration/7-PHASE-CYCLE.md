# 7-Phase Orchestration Cycle

The orchestration model defines how the platform runs from data ingestion through outbound activation. It is expressed as phases rather than public operational schedules.

## Phase 1: Data Ingestion

Source adapters extract data from generic ERP, CRM, payment, market, and regulatory sources. The ingestion pipeline stages, validates, transforms, and loads normalized records into the Customer 360 spine.

## Phase 2: Lead Intelligence

The Lead Intelligence layer enriches account and market coverage data, performs deterministic matching, identifies net-new opportunities, and publishes market-related signals.

## Phase 3: Classification

The Classification Engine applies deterministic value, behavior, and action-tag logic to the normalized account base.

## Phase 4: Cash Intelligence

The Cash Intelligence layer calculates payment conversion, DSO, aging movement, and anomaly signals.

## Phase 5: Narrative Synthesis

The Narrative Engine merges cross-agent outputs into audience-specific insight cards with source-backed claims.

## Phase 6: Dashboard Refresh

Dashboards and portfolio views refresh from governed outputs rather than raw source tables.

## Phase 7: Outbound Activation

Actionable signals are routed to workflow queues or collaboration tools through configurable tenant rules.

## Failure Policy

The orchestrator supports partial value delivery:

- Critical dependency failures stop downstream phases.
- Soft dependency failures degrade outputs but preserve auditability.
- Every run receives a run ID, status, and error summary.
- Recovery procedures restart from the last valid phase when possible.

