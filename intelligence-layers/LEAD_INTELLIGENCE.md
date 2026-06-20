# Lead Intelligence

Lead Intelligence answers: **Who should be in the addressable universe that is not yet represented in the account base?**

It combines external signal scanning, market-source ingestion, deterministic matching, and lead scoring to identify net-new opportunities, account closure risk, and addressable-market gaps.

## Inputs

- Existing account records from the Customer 360 spine.
- External business listings and location records.
- Provincial regulatory databases.
- Industry and establishment reference data.
- Tenant-specific matching thresholds and scoring weights.

## Core Logic

The matching engine uses three layers:

1. Exact match on normalized identifiers and business names.
2. Fuzzy match on name, address, and operating attributes.
3. Geo-radius match for location-level ambiguity.

Each candidate record is classified as one of:

- Existing matched account.
- Potential duplicate.
- Net-new lead.
- Closed or inactive business.
- External distress signal.
- License or coverage gap.

## Outputs

Lead Intelligence publishes signals such as:

- `EXTERNAL_CLOSURE`
- `EXTERNAL_DISTRESS`
- `LICENSE_GAP_DETECTED`
- `AR_AT_RISK`
- `CAPTURE_RATE_UPDATE`

## Governance Requirements

- Matching thresholds are tenant-configurable.
- Lead scoring rules are versioned.
- Every accepted match keeps the source record and match rationale.
- Human review is required for low-confidence matches before activation.

## Portfolio Value

This layer demonstrates bottom-up market discovery, auditable lead generation, and a practical bridge between external market data and internal revenue operations.

