# Cisco Secure Workload Master POV Process

## Purpose

This runbook defines the common process for starting and running a Cisco Secure Workload POV. Use the vertical runbooks to tailor discovery, scope design, evidence, and success criteria.

## Phase 0 - Qualification

### Goals

- Confirm the customer has a real workload visibility, segmentation, compliance, or incident response problem.
- Select one or two applications or environments, not the whole estate.
- Confirm a measurable outcome the customer cares about.

### Discovery Questions

- What application, business service, or regulated environment should the POV protect?
- What is the current segmentation method: firewall zones, VLANs, cloud security groups, NSGs, Kubernetes policies, manual diagrams, or none?
- Which teams own application, infrastructure, network, security, compliance, and change approval?
- Which pain matters most: unknown flows, audit evidence, lateral movement, policy drift, cloud migration, ransomware reduction, or compliance scope reduction?
- What would make the POV successful enough to justify expansion?

### Exit Criteria

- Named executive sponsor.
- Named technical owner.
- In-scope application or environment selected.
- Success criteria written in business language.
- Customer understands that the first phase is visibility and simulation, not immediate enforcement.

### Success Criteria Patterns

Use success criteria that prove a decision, not generic activity. Good POV criteria are measurable, scoped to one application or boundary, and tied to an owner.

| Category | Example success criteria |
|---|---|
| Visibility | CSW identifies expected and unexpected flows for one application over an agreed observation window |
| Ownership | At least one application owner validates the dependency map and approves the scope tree |
| Labels | Required labels exist for in-scope workloads: `app`, `env`, `owner`, `data_class`, `criticality`, and `compliance` |
| Risk | The POV identifies high-risk ports, plaintext protocols, unexpected egress, or vulnerable workloads with owner assignment |
| ADM | CSW generates a candidate policy from observed flows and the app team reviews it |
| Simulation | Policy simulation runs without enforcement impact and produces actionable violations |
| Enforcement | One bounded enforcement candidate is approved with rollback steps, if the customer is ready |
| Evidence | The final package includes inventory, scope, labels, flows, policy candidate, exceptions, and gaps |

## Phase 1 - Readiness and Access

### Required Inputs

- CSW SaaS tenant or cluster access.
- API key with the needed read and policy capabilities.
- Sensor installation path for Linux and Windows workloads.
- Change window or approval for sensor deployment.
- In-scope workload list, owner list, and existing network diagrams.
- Cloud connector permissions if AWS, Azure, or GCP are in scope.

### Technical Checks

- Confirm sensor compatibility for target OS versions.
- Confirm workloads can reach the CSW cluster on required outbound ports.
- Confirm endpoint protection tools will allow CSW sensor installation.
- Confirm proxy/TLS inspection requirements.
- Confirm time sync and DNS resolution.
- Confirm retention and data handling expectations.

## Phase 2 - Deployment

### Deployment Pattern

Start with monitoring only.

- Install sensors on representative workloads.
- Add cloud connectors where applicable.
- Validate telemetry.
- Confirm sensor health.
- Confirm flow, process, package, and vulnerability telemetry where licensed and supported.

### Recommended Initial Coverage

- One critical application.
- All tiers if possible: web, app, database, middleware, identity, management.
- One non-production environment first if production change controls are tight.
- A small production pilot once the customer sees stable telemetry.

## Phase 3 - Scope and Label Design

### Baseline Labels

- `app`
- `env`
- `owner`
- `data_class`
- `criticality`
- `compliance`
- `region`
- `lifecycle`

### Why Labels Are Required

CSW telemetry shows what is happening. Labels explain what it means. Labels connect workloads to applications, owners, environments, regulated data, and criticality. Without a label strategy, CSW can still show flows, but policy design and audit evidence become harder to trust and repeat.

### Label Source Strategy

| Source | When to use it | Why it helps | Risk |
|---|---|---|---|
| ServiceNow CMDB | Use when CI ownership, business service, and criticality fields are reliable | Aligns CSW scopes and findings to operational owners and change workflows | Inaccurate CMDB data can mislabel workloads |
| Active Directory / Entra ID | Use as enrichment for Windows servers, OUs, groups, and ownership hints | Helps infer environment, owner, admin group, or business unit | OU structure and naming standards may not match application reality |
| Cloud tags | Use for AWS, Azure, and GCP workloads where tagging is governed | Provides app, owner, environment, region, and cost-center context | Tags may be missing or inconsistent across accounts |
| Manual labels | Use for fast POV progress and unknown workloads | Lets the team build scopes before integrations are ready | Requires review and should not become unmanaged long-term data |
| CSV import/export | Use as a low-friction bridge | Fastest way to test a label model with app owners | Static files drift quickly |

### ServiceNow Integration Guidance

ServiceNow is valuable when it is the source of truth for applications, business services, ownership, support groups, criticality, or change records. In a POV, ServiceNow can be used in three maturity levels:

1. **Manual export/import:** Use a CSV from ServiceNow to label CSW workloads quickly.
2. **Operational workflow:** Use ServiceNow ownership and change records to route CSW findings and policy exceptions.
3. **Continuous integration:** Keep CMDB, CSW labels, and exception workflow synchronized after the POV.

Ask the customer to identify the ServiceNow fields that matter before kickoff:

- Business service.
- Application name.
- CI owner.
- Support group.
- Environment.
- Criticality.
- Data classification.
- Compliance scope.
- Change record or exception record.

### Active Directory and Manual Label Guidance

Active Directory is useful when Windows server names, OUs, groups, or admin assignments reflect business ownership. Use it to enrich labels, not to replace application owner validation.

Manual labels are acceptable in the POV when authoritative sources are incomplete. Keep them controlled:

- Document who applied the label.
- Document why it was applied.
- Review labels with the application owner.
- Mark temporary or uncertain labels clearly.
- Create a follow-up task to replace manual labels with CMDB, cloud tag, or identity-source data where possible.

### Scope Design

Build scopes around the protected service, not the network diagram.

Example:

```text
Customer
└── Production
    └── Payments
        ├── Web
        ├── App
        ├── Database
        ├── Shared-Services
        └── Third-Party-Egress
```

### Exit Criteria

- Scope tree reviewed with app owner and security owner.
- Labels mapped to customer inventory source.
- Known uninstrumented systems documented.
- Out-of-scope dependencies captured.

## Phase 4 - Visibility and Baseline

### Activities

- Run flow search for the observation window.
- Review top talkers, top ports, unmanaged dependencies, and internet egress.
- Validate application owners recognize the communication paths.
- Identify high-risk ports and plaintext protocols.
- Identify unexpected management access, lateral movement paths, and third-party communication.

### Evidence Artifacts

- Workload inventory export.
- Scope hierarchy export.
- Flow summary.
- Top conversations.
- High-risk port summary.
- Vulnerability or package exposure summary.
- Known gaps and assumptions.

## Phase 5 - ADM and Policy Simulation

### Activities

- Create ADM workspace for the selected application or scope.
- Choose an observation window that captures normal business cycles.
- Review discovered dependencies with the app team.
- Remove noise, backup windows, scanners, and temporary admin traffic where appropriate.
- Generate candidate policy.
- Simulate before enforcement.

### Exit Criteria

- Application owner approves dependency map.
- Security owner approves high-risk exceptions.
- Change owner understands enforcement plan.
- Policy simulation shows expected behavior.

## Phase 6 - Enforcement Candidate

### Enforcement Approach

Do not enforce everything at once.

- Start with low-risk deny candidates.
- Start with tightly bounded scopes.
- Prefer non-production first when possible.
- Use maintenance windows for production enforcement.
- Define rollback steps before enforcement.

### Minimum Enforcement Readiness

- Sensor health stable.
- Candidate policy approved.
- Backup and admin paths validated.
- Monitoring and alerting ready.
- Rollback procedure documented.
- Business owner signs off.

## Phase 7 - Evidence Package and Readout

### Technical Readout

- What was deployed.
- What was observed.
- What was unexpected.
- What policy was generated.
- What risk was reduced.
- What gaps remain.

### Executive Readout

- Business problem.
- Scope of POV.
- Before/after visibility.
- Risk findings.
- Compliance value.
- Expansion plan.
- Licensing and operational requirements.

## Phase 8 - Expansion Plan

### Expansion Paths

- More applications.
- More environments.
- Production enforcement.
- Cloud connectors.
- Compliance reporting.
- SIEM/SOAR integration.
- Incident response use cases.
- Vulnerability exposure prioritization.

### Final POV Decision

End with one of three recommendations:

- Expand visibility.
- Move selected scopes to enforcement.
- Pause until prerequisites are fixed.
