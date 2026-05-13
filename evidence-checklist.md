# CSW POV Evidence Checklist

Use this checklist for any Cisco Secure Workload POV, regardless of vertical.

## Readiness Evidence

- Customer sponsor and technical owner identified.
- In-scope application or environment selected.
- Success criteria documented.
- Sensor deployment plan approved.
- API and UI access confirmed.
- Cloud connector permissions confirmed, if applicable.
- Data handling and retention expectations documented.

## Deployment Evidence

- Sensor install list.
- Sensor health screenshot or export.
- Cloud connector status.
- Workloads with no telemetry.
- Workloads that cannot be instrumented.
- Known exclusions and compensating controls.

## Scope and Label Evidence

- Scope hierarchy export.
- Label taxonomy.
- Workload-to-scope mapping.
- Application owner validation.
- Regulated data or criticality mapping.
- Out-of-scope dependencies.

## Visibility Evidence

- Workload inventory export.
- Flow search summary.
- Top conversations.
- Top ports and protocols.
- Internet egress summary.
- Third-party communication summary.
- High-risk port findings.
- Plaintext protocol findings.
- Process/package/vulnerability summary where supported.

## ADM and Policy Evidence

- ADM workspace name and observation window.
- Discovered dependency map.
- Candidate policy.
- Removed noise and rationale.
- Required exceptions.
- Simulation results.
- Enforcement readiness decision.

## Risk and Gap Evidence

- Unknown or unexpected flows.
- Uninstrumented workloads.
- Unsupported platforms.
- High-risk ports.
- Plaintext protocols.
- Excessive east-west access.
- Vulnerability exposure.
- Policy exceptions without owner.
- Missing CMDB, SIEM, GRC, endpoint, or network integrations.

## Final Readout Evidence

- Executive summary.
- Technical findings.
- Before/after visibility story.
- Scope and labels.
- Flow and dependency maps.
- Policy candidate.
- Risk findings.
- Compliance mapping.
- Expansion plan.
- Commercial next step.

## Go / No-Go Decision

### Expand

Use when the POV produced useful visibility and the customer wants broader coverage.

### Enforce

Use when the application owner, security owner, and change owner approve a bounded policy candidate.

### Pause

Use when prerequisites are missing: poor sensor coverage, unclear app ownership, no change window, unsupported platforms, or unresolved operational risk.
