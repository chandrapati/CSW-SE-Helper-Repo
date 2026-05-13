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
