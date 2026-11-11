# Technical Documentation — Acme Payments

| Layer | Choice |
|-------|--------|
| API | Go 1.23 |
| DB | PostgreSQL 16 (multi-AZ, encrypted) |
| Cache | Redis (idempotency, ADR-0002) |
| Bus | SNS/SQS |
| Secrets | Vault (NFR-004) |
| Infra | EKS + Terraform (ADR-0001) |
| CI/CD | GitHub Actions + ArgoCD |

Interfaces: POST /v1/charges (idempotent), POST /v1/subscriptions, GET /v1/audit/{id}.
