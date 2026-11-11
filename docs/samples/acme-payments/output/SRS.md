# Software Requirements Specification — Acme Payments

## Functional
| ID | Requirement |
|----|-------------|
| REQ-001 | Tokenize card data; never persist PAN |
| REQ-002 | Multi-currency charge (USD, EUR, GBP) |
| REQ-003 | Idempotent charge API |
| REQ-004 | Signed outbound webhooks |
| REQ-005 | Immutable audit log |

## Non-functional
| ID | Requirement |
|----|-------------|
| NFR-001 | p95 < 300 ms |
| NFR-002 | 99.95% availability |
| NFR-003 | Multi-AZ; RPO <= 5 min, RTO <= 1 h (TBD) |
| NFR-004 | No secrets in source; Vault/KMS |
| NFR-005 | SAST + SCA + secret scan on PR |

## TBD
SOC 2 scope; final RTO/RPO; card-network certification roadmap.
