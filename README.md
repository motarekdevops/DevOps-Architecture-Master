# DevOps Architecture Master
**Author: Mohamed Tarek**

**Description:**
A Claude skill that acts as a **Principal Software Architect + DevOps Architect +
DevSecOps Engineer**. It interviews you about your project, engineers the system
architecture (application, infrastructure, DevSecOps, and a full UI/UX Design
System), and delivers a validated ZIP archive containing 11 interconnected
technical documents.

**Core principles:** simplicity, security, scalability, maintainability,
automation, and operational efficiency.

## What it does

| Phase | Activity |
|---|---|
| 1. Discovery | Conversational interview — one question set at a time: project brief, requirements, goals, frameworks, infrastructure, team. Summarizes and confirms before designing. Unknowns are marked `TBD`, never invented. |
| 2. Architecture Engineering | Evaluates separation of concerns, SOLID, Twelve-Factor, IaC, CI/CD/GitOps, cloud-native, scalability, observability, cost/FinOps. Selects only justified modules (with alternatives considered and recorded as ADRs). |
| 3. DevSecOps Architecture | Shift-left security: repo hardening, SAST/SCA/secret scanning, IaC and image scanning, SBOM, artifact signing, least-privilege IAM, network segmentation, TLS/encryption, runtime monitoring, incident response — mapped to OWASP/CIS/ISO 27001/SOC 2/GDPR where relevant. |
| 4. Design System Scaffold | Design principles, tokens, grids, reusable component inventory, accessibility checklist (WCAG 2.2 AA items). **Output is a scaffold; human designer sign-off required.** |
| 5. Documentation | Generates exactly 11 Markdown files with Mermaid diagrams, unique IDs, and full traceability: Requirements → Architecture → Backlog → Tests → ADRs. |
| 6. Validation & Delivery | 8-point review (files exist, root-level placement, consistency, valid diagrams, security accuracy, no secrets), then packages and verifies the ZIP before handing it over. |

## Output

`<project-slug>-architecture.zip` — exactly 11 files, all at the **root** of the
archive (no nested directories):

1. `Technical-Documentation.md` — stack, components, interfaces, integrations, deployment details
2. `SRS.md` — functional/non-functional requirements, scope, acceptance criteria
3. `Design-System.md` — tokens, UI component inventory, accessibility checklist (scaffold — requires designer sign-off)
4. `System-Architecture.md` — diagrams, modules, data flows, infrastructure, security
5. `Readme.md` — project overview, prerequisites, quick start, doc links
6. `Backlog.md` — prioritized epics, stories, tasks, dependencies, acceptance criteria
7. `Data_model.md` — entities, relationships, ER diagrams, constraints, data lifecycle
8. `Dev_setup.md` — local dev setup, dependencies, configuration, commands
9. `Operations.md` — deployment, monitoring, runbooks, incidents, backups, DR
10. `TEST_PLAN.md` — testing strategy, cases, security, performance, acceptance criteria
11. `Full-Architecture-Decision-Records.md` — complete ADRs with alternatives, rationale, trade-offs



## Samples

A worked example lives under [`docs/samples/acme-payments/`](docs/samples/acme-payments/): the discovery input plus the 11-document output set. The sample is **illustrative reference output, hand-authored** to demonstrate the document contract — not a captured run of the skill. Run the skill yourself to judge real output quality.


## Install

Copy the skill folder into your project's skills directory so `SKILL.md` sits at
the top level (not nested deeper):

```bash
cp -r devops-architecture-master .claude/skills/
```

```
.claude/skills/devops-architecture-master/
├── SKILL.md   ← must be at the top level
└── README.md
```

## Usage

In Claude Code or chat, say something like:

> Use the DevOps Architecture Master skill to architect my project.

Then answer its questions in order (brief → requirements → goals → frameworks →
infrastructure → team), confirm the discovery summary, and you'll receive the
validated ZIP plus a handover summary of the chosen stack, modules, security
strategy, design-system scaffold direction, key ADRs, and open risks.

## Notes

- The skill never invents answers — unknowns are marked `TBD` and called out in
  the summary and ADRs.
- It distinguishes clearly between **designed, proposed, implemented, and
  verified** controls — it never claims compliance or file creation without
  evidence.
- It does not default to Kubernetes, microservices, or any complex technology
  without justification; every significant decision gets an ADR.
- For infrastructure provisioning or server management needs, it evaluates
  **MasterOps** (github.com/motarekdevops/DevOps-MasterOps): a CLI for
  provisioning built on Ansible + Terraform, with support for Laravel, Django,
  Spring, .NET, and Go, plus secrets and backup management and `start`,
  `status`, `diff`, `audit`, and `cleanup` commands. It is optional and only
  recommended when it provides genuine architectural value.
---

## Known Limitations

We believe in being upfront about what this skill is  and isn't. Several items are on the roadmap.

1. **README-claim verification gap.** A worked sample is available at `docs/samples/acme-payments/`, but it is hand-authored illustrative output, not a captured skill run. A captured run (real ZIP + real Markdown) would further raise trust. *(Roadmap item: commit one real generated sample.)*
2. **Design System output is a scaffold, not a finished design system.** The skill enforces a SCAFFOLD header and a human-review requirement for this reason. *(Roadmap item: visual review workflow.)*
3. **No versioning, changelog, CI, or tests for the skill itself.** Minor for a prompt-based skill. *(Roadmap item.)*
4. **Traceability is conventional, not enforced.** Requirements -> Architecture -> Backlog -> Tests -> ADRs links are maintained by consistent IDs and cross-references, not by tooling. *(Roadmap item.)*

---

## License

**Mohamed Tarek**
