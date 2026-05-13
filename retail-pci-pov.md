# Retail and PCI CSW POV Process

## Best Fit Customers

- Retailers
- Ecommerce companies
- Restaurant and hospitality groups
- Payment processors
- Franchise operators

## Common Business Drivers

- PCI DSS scope reduction.
- CDE and CDE-connected segmentation.
- POS environment visibility.
- Store-to-data-center traffic validation.
- Ecommerce application dependency mapping.
- Third-party payment processor review.

## Recommended POV Scope

Pick one payment-relevant service:

- Ecommerce checkout.
- Payment gateway service.
- POS back-end service.
- Store support application.
- Tokenization or HSM-adjacent system.
- Logging, identity, or patching service connected to the CDE.

## Stakeholders

- PCI program owner.
- QSA or internal PCI lead.
- Network security.
- Application owner.
- Store IT or retail infrastructure.
- Platform / cloud team.
- Change manager.

## Discovery Questions

- What is currently in the CDE?
- Which systems are CDE-connected?
- Which systems are declared out of scope and why?
- What diagrams does the QSA rely on today?
- Which payment flows are expected from store, ecommerce, processor, and support systems?
- Which third-party processors or gateways are involved?
- What segmentation control is used today: firewall, VLAN, security group, NSG, workload policy, or none?

## Scope Pattern

```text
Retail-PCI
├── CDE
│   ├── Payment-Processing
│   ├── PAN-Storage
│   ├── Payment-Gateway
│   └── HSM-Adjacent
├── CDE-Connected
│   ├── Ecommerce-Web
│   ├── Store-Services
│   ├── Identity
│   └── Logging
├── Third-Party-Processors
└── Out-of-Scope-Validation
```

## Success Criteria

- Validate CDE and CDE-connected workload inventory.
- Produce a live CDE flow map.
- Identify communication between CDE and out-of-scope systems.
- Generate a least-privilege policy draft for one CDE application.
- Produce a QSA-friendly segmentation evidence package.

## Evidence Package

- CDE workload inventory.
- CDE-connected workload inventory.
- CDE flow diagram from observed telemetry.
- Third-party processor communication summary.
- High-risk port and plaintext protocol report.
- Policy simulation output.
- Exception register with owner and expiry date.
- Out-of-scope validation notes.

## Cisco Products That Help

- Cisco Secure Workload for CDE application mapping and microsegmentation.
- Cisco Secure Firewall for CDE perimeter enforcement.
- Cisco ISE for store/POS device network access.
- Cisco Secure Network Analytics for broader network behavior.
- Splunk for PCI log retention and reporting.
- Duo for privileged access MFA.

## Common Outside Products

- QSA assessment platform.
- Tenable, Qualys, or Rapid7 for ASV/vulnerability program alignment.
- File integrity monitoring where required.
- DLP or PAN discovery tools.
- HSM/key management platforms.

## Readout Narrative

"CSW helped the retail team move PCI segmentation from static diagrams to observed workload evidence, showing what belongs in the CDE, what connects to it, and where scope can be reduced or controls tightened."
