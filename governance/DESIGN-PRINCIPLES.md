# Design Principles

## Governance First

Governance is load-bearing architecture. RACI, access control, change approval, and audit trails are part of the system design, not post-implementation documentation.

## Deterministic Logic

Classification, scoring, matching, and routing are deterministic. The same input state should produce the same output, with versioned rules and documented thresholds.

## Signal Bus Over Direct Coupling

Agents communicate through append-only signals instead of direct calls. This preserves auditability and prevents hidden dependencies.

## Configuration Over Code

Tenant-specific behavior lives in reference tables:

- Field mappings.
- License and coverage matrices.
- Matching thresholds.
- Scoring weights.
- SLA and routing rules.
- Narrative visibility policies.

## Jurisdiction-Aware

The architecture is designed for regulated environments where data sources, reporting obligations, currency assumptions, and privacy controls vary by jurisdiction.

## Explainability

Every narrative, tag, and recommendation should be traceable to a rule, signal, source field, or run artifact.

## Public Reference Boundary

The public version avoids:

- Client names.
- Real customer names.
- Production financials.
- Secrets or credentials.
- Specific operational schedules.
- Proprietary implementation details.

