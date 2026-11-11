# Architecture Decision Records

## ADR-0001: Use Amazon EKS for container orchestration
- Status: Accepted
- Context: 2 backend services; team of 8 with SRE; multi-AZ.
- Decision: EKS (managed control plane).
- Alternatives: ECS Fargate (weaker mesh/mTLS); EC2+kubeadm (ops burden).
- Consequences: + rollouts/autoscaling/mesh; - cost, cognitive load.

## ADR-0002: Idempotency strategy
- Status: Accepted
- Context: REQ-003 requires safe retries.
- Decision: Idempotency-Key; Redis dedupe (TTL 24h) + unique DB constraint.
- Alternatives: DB-only (lock contention); none (violates REQ-003).
- Consequences: + safe retries; - Redis dependency.

## ADR-0003: mTLS via service mesh
- Status: Proposed
- Context: PCI-adjacent internal traffic; no dedicated security engineer.
- Decision: Istio mTLS between services.
- Alternatives: Manual TLS (ops-heavy); none (rejected).
- Consequences: + encryption in transit; - mesh complexity.
