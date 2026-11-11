# Operations — Acme Payments

Deployment: ArgoCD sync; blue/green; rollback = revert tag (RTO <= 1 h, NFR-003).
Monitoring: latency (NFR-001), availability (NFR-002), idempotency dupes.
Runbooks: charge stuck pending; idempotency collision (ADR-0002); secret rotation.
Backup/DR: PG PITR (RPO <= 5 min), quarterly drill (NFR-003).
