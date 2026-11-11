# Data Model — Acme Payments

| ID | Entity | Key fields |
|----|--------|-----------|
| ENT-001 | charges | id, idempotency_key, amount, currency, status |
| ENT-002 | audit_log | id, charge_id, from_state, to_state, ts |
| ENT-003 | fx_snapshots | id, pair, rate, ts |
| ENT-004 | subscriptions | id, customer_id, plan_id, status |
| ENT-005 | customers | id, merchant_id, email |

Lifecycle: pending -> authorized -> captured|failed. Audit rows append-only.
