# Manufacturing and OT-Adjacent CSW POV Process

## Best Fit Customers

- Manufacturers
- Energy and utilities
- Pipeline operators
- Industrial companies
- Logistics and transportation providers
- OT-adjacent IT teams

## Common Business Drivers

- Ransomware blast-radius reduction.
- IT/OT segmentation evidence.
- NERC CIP or IEC 62443 support.
- TSA Pipeline Security Directive support.
- Vendor and remote access visibility.
- Patch, backup, identity, and jump-host protection.

## Recommended POV Scope

Do not start with PLCs or unmanaged OT endpoints. Start with IT-side systems that support OT.

- Jump hosts.
- Patch repositories.
- Backup servers.
- Historians on Windows/Linux.
- Identity and PKI services.
- Vendor access systems.
- Engineering workstation support systems.
- Monitoring and logging systems.

## Stakeholders

- CISO / security architecture.
- OT security.
- Plant operations.
- Network security.
- Infrastructure owner.
- Compliance / regulatory.
- Change advisory or maintenance window owner.

## Discovery Questions

- Which IT systems can affect OT availability or safety?
- Which systems bridge corporate IT and OT environments?
- Which vendors connect remotely?
- Which jump hosts, patch servers, backup systems, and identity services support OT?
- Which workloads can safely run CSW sensors?
- Which systems require passive-only or compensating controls?
- Which regulatory driver matters: NERC CIP, TSA, IEC 62443, internal risk, or ransomware?

## Scope Pattern

```text
Manufacturing-OT-Adjacent
├── OT-Facing-IT
│   ├── Jump-Hosts
│   ├── Vendor-Access
│   ├── Patch-Repositories
│   ├── Backup
│   ├── Identity-PKI
│   └── Monitoring
├── Site
│   ├── Plant-01
│   ├── Plant-02
│   └── Data-Center
└── Exceptions
    ├── Cannot-Instrument
    └── Compensating-Control
```

## Success Criteria

- Map IT-side systems that support OT operations.
- Identify unexpected IT-to-OT and OT-facing communications.
- Document vendor and remote access paths.
- Generate policy candidates for jump hosts, patch repositories, and backup services.
- Produce a segmentation gap list that distinguishes CSW-covered systems from OT-specific controls.

## Evidence Package

- OT-facing IT workload inventory.
- Site and function scope hierarchy.
- Vendor access flow summary.
- Jump-host and patch-repo dependency map.
- High-risk port and plaintext protocol findings.
- Cannot-instrument list.
- Compensating-control register.
- Candidate policy and enforcement readiness notes.

## Cisco Products That Help

- Cisco Secure Workload for IT-side workload segmentation.
- Cisco Cyber Vision for OT asset and protocol visibility.
- Cisco Secure Firewall for IT/OT boundary enforcement.
- Cisco ISE for user/device access and network admission.
- Cisco Secure Network Analytics for network behavior.
- Splunk or XDR for investigation and evidence correlation.

## Common Outside Products

- Claroty, Nozomi, Dragos, or other OT monitoring if Cyber Vision is not deployed.
- Data diodes or unidirectional gateways where required.
- OT firewall platforms or existing industrial boundary controls.
- NERC CIP / IEC 62443 GRC workflows.
- PAM platforms for vendor access control.

## Readout Narrative

"CSW helped the manufacturing team protect the IT systems that OT depends on, while clearly separating what CSW can enforce from what requires OT-native monitoring, boundary controls, and operational approval."
