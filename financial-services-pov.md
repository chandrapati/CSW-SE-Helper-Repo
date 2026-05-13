# Financial Services CSW POV Process

## Best Fit Customers

- Banks
- Insurance companies
- Fintech platforms
- Payment processors
- Capital markets and trading platforms
- Financial SaaS providers

## Common Business Drivers

- DORA operational resilience.
- PCI DSS CDE segmentation.
- SWIFT CSCF evidence.
- SOC 2 customer assurance.
- Ransomware blast-radius reduction.
- Merger, cloud migration, or data center modernization.
- Third-party and vendor access visibility.

## Recommended POV Scope

Pick one high-value environment:

- Payment application.
- Online banking application.
- Trading support service.
- SWIFT-connected support systems.
- Identity or privileged access service.
- Important Business Function under DORA.

## Stakeholders

- CISO or security architecture.
- Infrastructure / platform owner.
- Application owner.
- Network security.
- Compliance / risk.
- Internal audit.
- Change manager.

## Discovery Questions

- Which applications support critical financial operations or Important Business Functions?
- Which workloads store, process, or transmit cardholder data or regulated financial data?
- Which third parties connect to the application?
- Which systems are considered CDE, CDE-connected, SWIFT-supporting, or production-supporting?
- What segmentation evidence does audit ask for today?
- Where are network diagrams or firewall rules known to be inaccurate?
- What is the customer's biggest concern: audit, ransomware, cloud migration, or policy drift?

## Scope Pattern

```text
Financial-Services
├── Payments
│   ├── CDE
│   ├── CDE-Connected
│   ├── Security-Services
│   └── Third-Party-Processors
├── Online-Banking
│   ├── Web
│   ├── App
│   ├── Database
│   └── Identity-Dependencies
├── SWIFT-Support
│   ├── Jump-Hosts
│   ├── File-Transfer
│   └── Monitoring
└── DORA-IBF
    ├── Critical
    ├── Supporting
    └── Third-Party-Egress
```

## Success Criteria

- Produce a current dependency map for one regulated financial application.
- Identify unauthorized or unexpected communication paths.
- Generate candidate least-privilege policy from observed flows.
- Document CDE, SWIFT-supporting, or IBF-supporting workload boundaries.
- Produce an audit-ready evidence package for the selected scope.

## Evidence Package

- In-scope workload inventory.
- Scope hierarchy.
- Top application flows.
- Third-party and external egress summary.
- High-risk ports and plaintext protocol findings.
- ADM-generated policy draft.
- Policy exception list with owner and business justification.
- Segmentation gap report.

## Cisco Products That Help

- Cisco Secure Workload for workload visibility and microsegmentation.
- Cisco Secure Firewall for perimeter and zone enforcement.
- Cisco Secure Network Analytics for network behavior.
- Splunk for long-term evidence and audit correlation.
- Duo for privileged and third-party access MFA.
- Cisco ISE for campus/device access context.

## Common Outside Products

- Archer, ServiceNow GRC, or AuditBoard for audit workflow.
- Tenable, Qualys, or Rapid7 for vulnerability program alignment.
- CyberArk, BeyondTrust, or Delinea for privileged access evidence.
- Thales, Entrust, Venafi, or DigiCert for cryptography and certificate evidence.

## Readout Narrative

"CSW helped convert a static financial services segmentation discussion into a live workload evidence package: what is in scope, what communicates, what should be allowed, what is risky, and what can move toward enforcement."
