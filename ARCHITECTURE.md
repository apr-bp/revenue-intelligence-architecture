# Architecture Overview

RI OS is a reference architecture for a governed Revenue Intelligence operating system. It is designed to show how a RevOps function can move from fragmented reporting to an auditable decision layer across account health, market coverage, payment behavior, and executive narrative.

The architecture is multi-tenant by design. Tenant-specific behavior is controlled through configuration tables: field mappings, matching thresholds, classification rules, scoring weights, service-level policies, and narrative visibility rules.

## Core Pattern

```text
Source adapters
  -> ingestion pipeline
  -> normalized Customer 360 spine
  -> intelligence layers
  -> append-only signal bus
  -> narrative synthesis
  -> dashboards and workflows
```

## Customer 360 Spine

The Customer 360 spine is the normalized operating layer used by all intelligence modules. It contains abstract account, invoice, payment, classification, external-market, and workflow entities. The spine avoids embedding business logic directly into raw source data.

## Intelligence Layers

| Layer | Primary Question | Output |
| --- | --- | --- |
| Lead Intelligence | Who should be in the addressable universe? | Lead, closure, distress, and market-gap signals |
| Classification | Which accounts are at risk, growing, or leaking? | Deterministic action tags and confidence scores |
| Cash Intelligence | Where is cash sitting, how long, and what is changing? | DSO, anomaly, payment trend, and cash-health signals |
| Narrative Engine | What should each audience understand and do? | Audited, role-specific insight cards |

## Signal Bus

Agents do not call each other directly. They publish signals to an append-only bus with a strict contract: signal type, source layer, target layer, severity, confidence, payload, run ID, tenant ID, and expiry policy.

This creates a full audit trail and lets each layer evolve independently.

## Governance Layer

Governance is treated as architecture, not documentation. Ownership, approval paths, role visibility, and change control are modeled as part of the operating system.

Key controls include:

- RACI ownership for each layer.
- Versioned rules and thresholds.
- Run-level audit trails.
- Row-level security for tenant isolation.
- Role-based narrative visibility.
- Explicit data lineage from narrative claim back to source field.

## Public Reference Boundaries

This repository intentionally uses generic business entities and abstract schemas. It does not include live customer data, implementation credentials, client identifiers, production schedules, or proprietary operating procedures.

