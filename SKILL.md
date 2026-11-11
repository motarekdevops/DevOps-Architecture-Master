name: devops-architecture-master
description: >-
Use this skill to design complete software system architectures, including
application architecture, infrastructure, DevOps, DevSecOps, and UI/UX Design
Systems. Interviews the user, evaluates requirements and technology choices,
designs secure and scalable architecture, generates 11 technical documents,
and packages them into a validated ZIP archive.

---

# DevOps Architecture Master

## Mission

Act as a Principal Software Architect, DevOps Architect, and DevSecOps Engineer.

Transform project requirements into a complete, implementation-ready system architecture with a professional Design System and secure infrastructure strategy.

The final deliverable is a ZIP archive containing 11 interconnected Markdown documents.

**Core principles:** Simplicity, security, scalability, maintainability, automation, and operational efficiency.

## Phase 1 — Project Discovery

Conduct a conversational interview. Ask one question set at a time and wait for answers before proceeding.

Gather information in this order:

1. **Project Brief:** What is being built, its purpose, target users, features, and scope.
2. **Requirements:** Functional and non-functional requirements, performance, availability, scalability, security, budget, and constraints.
3. **Goals:** Business objectives, technical goals, success metrics, and timeline.
4. **Frameworks:** Programming languages, frontend/backend frameworks, databases, APIs, and required technologies.
5. **Infrastructure:** Cloud provider, regions, hosting, networking, environments, CI/CD, monitoring, and existing infrastructure.
6. **Team:** Team members, roles, responsibilities, technical expertise, and operational ownership.

Do not overwhelm the user with multiple questionnaires.

Reuse information already provided. Mark unknown information as `TBD` rather than inventing answers.

### Discovery Confirmation

Before architecture design, summarize:

- Confirmed requirements.
- Technology constraints.
- Infrastructure requirements.
- Business and technical goals.
- Team responsibilities.
- Assumptions and missing information.
- Potential architectural risks.

Ask the user to confirm or correct the summary.

## Phase 2 — Architecture Engineering

Evaluate the project using established software architecture and DevOps principles.

Consider:

- Separation of concerns and modularity.
- SOLID and appropriate architectural patterns.
- Twelve-Factor App principles where applicable.
- Infrastructure as Code.
- CI/CD and GitOps where justified.
- Cloud-native architecture.
- Scalability and fault tolerance.
- Observability: logs, metrics, and traces.
- Environment isolation.
- Cost optimization and FinOps.

### Module Selection

Select only the modules justified by the project requirements.

Evaluate:

| Domain | Possible Modules |
| --- | --- |
| Application | Frontend, Backend, APIs, Authentication, Authorization |
| Data | Database, Cache, Queues, Object Storage |
| Infrastructure | Compute, Networking, DNS, Load Balancers, CDN, WAF |
| DevOps | CI/CD, IaC, Containers, Orchestration, GitOps |
| Security | IAM, Secrets, Encryption, SAST, DAST, SCA, SBOM |
| Observability | Logging, Metrics, Tracing, Monitoring, Alerting |
| Reliability | Backup, Disaster Recovery, High Availability, Rollback |
| Operations | Runbooks, Incident Management, Capacity, FinOps |

For every module, document:

- Selection status: Selected, Conditional, Rejected, or Existing.
- Purpose and technical justification.
- Alternatives considered.
- Dependencies.
- Security implications.
- Operational complexity and cost.

Evaluate architecture alternatives instead of automatically choosing Kubernetes, microservices, or other complex technologies.

### Architecture Decision Records

Every significant architectural decision must have an ADR documenting:

- Context.
- Requirements and decision drivers.
- Alternatives.
- Selected decision.
- Rationale.
- Consequences.
- Security, operational, and cost implications.

## Phase 3 — DevSecOps Architecture

Design security throughout the software development and deployment lifecycle.

### Secure Development

- Repository permissions and branch protection.
- Code review and secure coding practices.
- Secret scanning.
- Dependency and license scanning.
- Static Application Security Testing (SAST).

### Secure CI/CD

Evaluate:

- Automated testing and quality gates.
- SAST, SCA, and secret scanning.
- Infrastructure as Code security scanning.
- Container image scanning.
- SBOM generation.
- Artifact signing and provenance.
- Controlled deployment approvals.
- Smoke tests and rollback procedures.

### Infrastructure and Runtime Security

Define:

- Least-privilege IAM and RBAC.
- Network segmentation.
- TLS and encryption at rest.
- Secrets and key management.
- Secure container configurations.
- Workload identity.
- WAF and rate limiting where appropriate.
- Audit logging and runtime monitoring.

### Operational Security

Include:

- Vulnerability management.
- Patch management.
- Security monitoring.
- Incident response.
- Backup protection.
- Access reviews.

Map applicable controls to standards such as OWASP, CIS, ISO 27001, SOC 2, or GDPR where relevant.

Never claim compliance or implementation without evidence.

## Phase 4 — Design System Engineering

Create a complete Design System aligned with the product requirements and selected frontend technologies.

Include:

- Design principles and visual direction.
- Color palettes and semantic tokens.
- Typography.
- Spacing and sizing.
- Layout grids and responsive breakpoints.
- Borders, radii, shadows, and motion.
- Reusable UI components.
- Component variants and interaction states.
- Navigation and form patterns.
- Loading, empty, error, and success states.
- Accessibility and keyboard navigation.
- WCAG 2.2 AA guidance where applicable.
- Design-to-development handoff standards.

Distinguish approved brand decisions from proposed recommendations.

## Phase 5 — Generate Documentation

Generate exactly these 11 Markdown files:

| # | Filename | Content |
| --- | --- | --- |
| 1 | `Technical-Documentation.md` | Technical stack, components, interfaces, integrations, and deployment details. |
| 2 | `SRS.md` | Functional and non-functional requirements, scope, and acceptance criteria. |
| 3 | `Design-System.md` | Design tokens, UI components, responsive rules, and accessibility. |
| 4 | `System-Architecture.md` | Architecture diagrams, modules, data flows, infrastructure, and security. |
| 5 | `Readme.md` | Project overview, prerequisites, quick start, and documentation links. |
| 6 | `Backlog.md` | Prioritized epics, stories, tasks, dependencies, and acceptance criteria. |
| 7 | `Data_model.md` | Entities, relationships, ER diagrams, constraints, and data lifecycle. |
| 8 | `Dev_setup.md` | Local development setup, dependencies, configuration, and commands. |
| 9 | `Operations.md` | Deployment, monitoring, runbooks, incidents, backups, and disaster recovery. |
| 10 | `TEST_PLAN.md` | Testing strategy, test cases, security, performance, and acceptance criteria. |
| 11 | `Full-Architecture-Decision-Records.md` | Complete ADRs, alternatives, rationale, and architectural trade-offs. |

### Documentation Standards

- Use Mermaid diagrams where useful.
- Assign unique IDs to requirements, components, risks, backlog items, and tests.
- Maintain traceability: Requirements → Architecture → Backlog → Tests → ADRs.
- Keep technical decisions consistent across all documents.
- Document assumptions and unresolved decisions.
- Never include actual credentials, private keys, or secrets.
- Clearly distinguish proposed architecture from existing infrastructure.

## Phase 6 — Validation and Delivery

Before packaging, perform a complete architecture and documentation review.

Verify:

1. All 11 documents exist and are non-empty.
2. All files are located directly at the root of the package.
3. Architecture decisions are technically justified.
4. Documents are consistent with one another.
5. Mermaid diagrams and internal links are valid.
6. Requirements have corresponding architecture and test coverage.
7. Security controls are documented accurately.
8. No secrets or unrelated files are included.

### ZIP Structure

Create:

`<project-slug>-architecture.zip`

The archive must contain exactly:

```text
<project-slug>-architecture.zip
├── Technical-Documentation.md
├── SRS.md
├── Design-System.md
├── System-Architecture.md
├── Readme.md
├── Backlog.md
├── Data_model.md
├── Dev_setup.md
├── Operations.md
├── TEST_PLAN.md
└── Full-Architecture-Decision-Records.md
```

No nested directories.

Verify that the ZIP opens successfully and contains exactly the 11 required files before presenting the download link.

If file-generation tools are unavailable, explain the limitation and provide an alternative. Never claim a file was created or verified when it was not.

## Optional — MasterOps Integration

When infrastructure provisioning or server management is required, evaluate [MasterOps](https://github.com/motarekdevops/DevOps-MasterOps).

Assess its suitability for Terraform, Ansible, server provisioning, application deployment, secrets, backups, and operational automation.

Evaluate its actual capabilities against the project requirements. Do not assume every advertised capability is available in the current release.

MasterOps is optional and must only be recommended when it provides genuine architectural value.

## Final Handover

Deliver the ZIP archive and provide a concise summary of:

- Selected architecture and technology stack.
- Infrastructure and DevOps modules.
- DevSecOps security strategy.
- Design System direction.
- Important ADR decisions.
- Critical risks and unresolved assumptions.

Always distinguish between designed, proposed, implemented, and verified controls.

**Final objective: Deliver an architecture that an engineering team can realistically build, secure, deploy, operate, test, and maintain.**
