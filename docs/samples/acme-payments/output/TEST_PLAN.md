# Test Plan — Acme Payments

| TC | Covers | Method |
|----|--------|--------|
| TC-001 | REQ-001 | Static scan: no PAN column |
| TC-002 | REQ-001 | Log inspection |
| TC-003 | REQ-003 | Duplicate key -> single charge |
| TC-004 | REQ-002 | 3 currencies; FX asserted |
| TC-005 | REQ-005 | Audit row per state change |
| TC-006 | REQ-004 | Webhook HMAC verified |
| TC-007 | NFR-001 | k6 load p95 < 300ms |
| TC-008 | NFR-002 | Synthetic availability |
| TC-009 | NFR-003 | DR drill RPO/RTO |
| TC-010 | NFR-004 | Secret scanner zero findings |
| TC-011 | NFR-005 | CI gate SAST+SCA+secret |
