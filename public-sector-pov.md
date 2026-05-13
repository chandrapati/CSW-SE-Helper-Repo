# Public Sector CSW POV Process

## Best Fit Customers

- Federal agencies
- State and local government
- Higher education
- Defense contractors
- Regulated public-sector SaaS providers

## Common Business Drivers

- NIST SP 800-53 evidence.
- FedRAMP readiness.
- CMMC / CUI enclave segmentation.
- Zero Trust Architecture.
- Ransomware resilience.
- High-value asset protection.
- Continuous diagnostics and mitigation support.

## Recommended POV Scope

Pick one system boundary:

- FISMA system.
- FedRAMP moderate or high workload set.
- CUI enclave.
- High-value asset.
- Identity or privileged access service.
- Mission application.

## Stakeholders

- Authorizing official representative.
- ISSO / ISSM.
- System owner.
- Security architect.
- Infrastructure / cloud owner.
- SOC / incident response.
- Compliance / audit.

## Discovery Questions

- What is the formal system boundary?
- Which impact level or CMMC level applies?
- Which workloads process CUI, mission, or high-value data?
- Which SSP components are application, database, management, identity, and logging?
- Which controls need better technical evidence?
- Which systems are unsupported, unmanaged, or excluded from instrumentation?
- What evidence must support ATO, continuous monitoring, or assessment?

## Scope Pattern

```text
Public-Sector
├── System-Boundary
│   ├── Moderate
│   ├── High
│   ├── App-Tier
│   ├── Data-Store
│   ├── Management
│   └── Shared-Services
├── CUI-Enclave
│   ├── CUI-Systems
│   ├── CUI-Connected
│   └── External-Services
└── ZTA-Resources
    ├── Protected-Resources
    ├── Policy-Enforced-Flows
    └── Exceptions
```

## Success Criteria

- Map CSW scopes to the system boundary or CUI enclave.
- Produce workload-level evidence for selected AC, AU, CM, RA, SC, and SI controls.
- Generate candidate policy for one protected application or enclave.
- Identify segmentation gaps that affect ATO or assessment readiness.
- Create an expansion plan for continuous monitoring.

## Evidence Package

- System boundary workload inventory.
- SSP component mapping.
- CUI or mission system scope tree.
- Flow evidence by application tier.
- High-risk ports and plaintext protocol report.
- Vulnerability exposure summary.
- Policy simulation and exceptions.
- Control-to-evidence mapping.

## Cisco Products That Help

- Cisco Secure Workload for system boundary workload visibility and segmentation.
- Cisco ISE for user/device access context.
- Cisco Secure Firewall for boundary enforcement.
- Cisco Secure Endpoint and XDR for endpoint/investigation context.
- Splunk for retention and control evidence.
- Duo for MFA and privileged access.

## Common Outside Products

- eMASS, Xacta, Archer, ServiceNow GRC, or other ATO/GRC platforms.
- Tenable.sc, Qualys, Rapid7, Wiz, or Prisma Cloud for vulnerability posture.
- SailPoint, Saviynt, Entra ID, Okta, or Ping for identity governance.
- Backup and recovery platforms.
- Data classification and CUI marking tools.

## Readout Narrative

"CSW helped the public-sector team translate the formal system boundary into live workload evidence, showing communication paths, policy candidates, risk exposure, and gaps that matter to ATO or assessment readiness."
