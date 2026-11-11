# System Architecture — Acme Payments

Covers REQ-001, REQ-003, NFR-002.

## Components
| Component | Responsibility |
|-----------|----------------|
| charge-service | Charge orchestration, idempotency |
| subscription-service | Plans, customers, entitlements |
| webhook-dispatcher | Signed webhook delivery |
| PostgreSQL | Durable ledger + audit |
| Redis | Idempotency dedupe cache |

## Data flows
1. Client -> API Gateway -> charge-service
2. charge-service -> tokenization provider
3. charge-service -> PostgreSQL + Redis
4. charge-service -> SNS/SQS -> webhook-dispatcher -> merchant

## Security controls (designed/proposed/implemented/verified)
| Control | Status |
|---------|--------|
| mTLS service-to-service | designed (ADR-0003) |
| Least-privilege IAM | designed |
| Secret rotation | proposed |
| SAST in CI | designed |

## ADR refs
ADR-0001 (EKS), ADR-0002 (idempotency), ADR-0003 (mTLS).
