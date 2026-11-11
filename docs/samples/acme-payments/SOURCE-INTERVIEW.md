# Source Interview — Acme Payments

## 1. Project brief
B2B subscription billing and payment orchestration for SMB SaaS.

## 2. Requirements
- Functional: tokenize cards (never persist PAN), multi-currency (USD/EUR/GBP),
  idempotent charge API, signed webhooks, immutable audit log.
- Non-functional: p95 < 300ms, 99.95% availability, multi-AZ, no secrets in
  source, SAST+SCA+secret scan on every PR.
- Constraints: no dedicated security engineer; sub-$8k/mo at 500k charges.

## 3. Goals
Launch to 50 SMB merchants in 2 quarters; PCI-DSS-adjacent posture (designed
toward, not certified); SOC 2 readiness later.

## 4. Frameworks
Go 1.23, PostgreSQL 16, React + TypeScript, REST/OpenAPI 3.1, Redis for dedupe.

## 5. Infrastructure
AWS, EKS (managed control plane), Terraform, GitHub Actions, ArgoCD, Vault,
Prometheus + Grafana + OpenTelemetry, separate AWS accounts per environment.

## 6. Team
2 platform, 4 backend, 2 frontend, 1 SRE. No dedicated security engineer.

## 7. Unknowns (TBD)
- Final SOC 2 scope
- Final DR RTO/RPO
- Card-network certification roadmap
- Chargeback arbitration UI (out of scope for v1)
