# Generic Data Model

This schema is intentionally abstract. It describes the public-safe entities needed for a multi-tenant Revenue Intelligence architecture without exposing real customer records or production table definitions.

## Core Entities

### `tenants`

Represents an isolated business environment.

- `tenant_id`
- `tenant_name`
- `status`
- `created_at`
- `configuration_version`

### `accounts`

Represents an account or business entity.

- `account_id`
- `tenant_id`
- `normalized_name`
- `segment`
- `status`
- `industry_code`
- `region`
- `created_at`
- `updated_at`

### `invoices`

Represents billed obligations.

- `invoice_id`
- `tenant_id`
- `account_id`
- `invoice_date`
- `due_date`
- `amount_band`
- `currency`
- `status`

### `payments`

Represents received payments.

- `payment_id`
- `tenant_id`
- `account_id`
- `invoice_id`
- `payment_date`
- `payment_method`
- `amount_band`
- `currency`

### `classifications`

Stores deterministic account classification outputs.

- `classification_id`
- `tenant_id`
- `account_id`
- `run_id`
- `value_tier`
- `payment_behavior`
- `strategic_tag`
- `confidence_score`
- `rule_version`

### `signals`

Stores cross-agent messages.

- `signal_id`
- `tenant_id`
- `run_id`
- `signal_type`
- `source_layer`
- `target_layer`
- `severity`
- `confidence_score`
- `payload`
- `created_at`
- `expires_at`

### `narratives`

Stores role-specific insight cards.

- `narrative_id`
- `tenant_id`
- `run_id`
- `audience`
- `pattern_type`
- `summary`
- `recommended_action`
- `source_signal_ids`
- `visibility_role`

## Security Model

- Every table is tenant-scoped.
- PostgreSQL row-level security enforces tenant isolation.
- Sensitive financial and account-level fields are role restricted.
- Audit fields preserve run lineage and change history.

