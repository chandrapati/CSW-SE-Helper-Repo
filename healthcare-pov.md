# Healthcare CSW POV Process

## Best Fit Customers

- Hospitals and health systems
- Clinics and ambulatory care organizations
- Payers and insurance administrators
- Life sciences and clinical research
- Business associates handling ePHI

## Common Business Drivers

- HIPAA Security Rule evidence.
- HITRUST readiness.
- ePHI segmentation.
- Ransomware lateral-movement reduction.
- Biomedical / clinical application dependency visibility.
- Business associate and partner egress control.
- Legacy Windows and unsupported system exposure review.

## Recommended POV Scope

Pick one clinical or ePHI-bearing service:

- EHR-supporting application.
- Billing or claims platform.
- PACS / imaging environment.
- HL7 integration engine.
- Clinical data warehouse.
- Identity, patching, or backup service supporting ePHI systems.

## Stakeholders

- CISO / security operations.
- Clinical application owner.
- Infrastructure owner.
- Network/security architecture.
- Compliance / privacy officer.
- Biomedical engineering if medical devices are adjacent.
- Change advisory board.

## Discovery Questions

- Which systems store, process, transmit, or support ePHI?
- Which applications are most critical to clinical care?
- Which workloads are legacy, unsupported, or hard to patch?
- Which business associates or external partners communicate with ePHI systems?
- Which flows are known and approved: HL7, DICOM, database, LDAP, backup, monitoring?
- Which systems cannot be instrumented and need compensating controls?
- What evidence would help the privacy or compliance team during a HIPAA review?

## Scope Pattern

```text
Healthcare
├── ePHI-Zone
│   ├── EHR
│   ├── Billing
│   ├── Claims
│   ├── PACS
│   └── HL7-Integration
├── Clinical-Support
│   ├── Identity
│   ├── Patch-Management
│   ├── Backup
│   └── Monitoring
├── Biomedical-Adjacent
└── BAA-Partner-Egress
```

## Success Criteria

- Confirm ePHI workload inventory and scope boundaries.
- Identify unexpected ePHI access paths.
- Identify plaintext or high-risk clinical communication.
- Generate a policy candidate for one ePHI-bearing application.
- Produce an evidence pack that supports HIPAA risk analysis and technical safeguard discussions.

## Evidence Package

- ePHI workload inventory.
- Scope and label map.
- EHR / billing / PACS / HL7 dependency map.
- External partner communication summary.
- Plaintext protocol and high-risk port findings.
- Vulnerability exposure summary for in-scope workloads.
- Policy draft and exception register.
- Gaps requiring biomedical, endpoint, network, or GRC controls.

## Cisco Products That Help

- Cisco Secure Workload for workload visibility and segmentation.
- Cisco Cyber Vision for biomedical and OT visibility.
- Cisco Secure Firewall for zone and partner access enforcement.
- Cisco ISE for clinical device and user access control.
- Cisco Duo for privileged and remote access.
- Splunk or Cisco XDR for investigation and evidence correlation.

## Common Outside Products

- Epic, Cerner, PACS, or clinical application-native audit controls.
- Microsoft Purview, BigID, or DLP for data classification.
- ServiceNow GRC, Archer, or OneTrust for privacy and audit workflow.
- CrowdStrike, Defender, SentinelOne, Tenable, Qualys, or Rapid7 for endpoint and vulnerability program alignment.

## Readout Narrative

"CSW helped the healthcare team prove which workloads support ePHI, which flows are expected, which paths are risky, and where technical safeguards can be strengthened without disrupting patient care."
