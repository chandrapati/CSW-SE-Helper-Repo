# Cisco Secure Workload POV Runbooks

Reusable proof-of-value process runbooks for Cisco Secure Workload (CSW).

Use this repository when starting a new CSW POV and you need a clear process for
discovery, scope design, sensor rollout, visibility, ADM, segmentation policy,
evidence collection, and executive readout.

## Runbooks

- `master-pov-process.md` - common CSW POV process for any customer.
- `first-meeting-discovery-runbook.md` - first customer meeting flow and vertical-specific discovery questions for the SA.
- `financial-services-pov.md` - banks, insurers, fintech, payments, DORA, PCI, SWIFT, SOC 2.
- `healthcare-pov.md` - providers, payers, life sciences, HIPAA, HITRUST, ePHI.
- `it-services-pov.md` - MSPs, SaaS, outsourcing, SOC 2, ISO 27001, customer tenant isolation.
- `retail-pci-pov.md` - retail, ecommerce, POS, stores, PCI DSS.
- `public-sector-pov.md` - government, education, FedRAMP, NIST 800-53, CMMC.
- `manufacturing-ot-pov.md` - manufacturing, energy, utilities, OT-adjacent IT, NERC CIP, IEC 62443.
- `evidence-checklist.md` - common evidence artifacts and exit criteria.

## POV Philosophy

A CSW POV should prove a small number of high-value outcomes:

1. The customer can see workload inventory and communication paths they cannot reliably see today.
2. The customer can build scopes and labels that match business, application, and compliance boundaries.
3. ADM can convert observed flows into a defensible policy starting point.
4. Policy simulation and enforcement can reduce risk without breaking the application.
5. The final readout can tie technical evidence to business, security, and compliance outcomes.

## Standard POV Duration

Most POVs fit a 3- to 6-week motion:

- Week 0: qualification and readiness.
- Week 1: kickoff, access, cluster readiness, and sensor deployment.
- Week 2: visibility, inventory, labels, and scope design.
- Week 3: ADM, application dependency mapping, and policy simulation.
- Week 4: enforcement candidate review and evidence package.
- Week 5-6: optional enforcement pilot, executive readout, and expansion plan.

## Important Caveat

These runbooks are sales engineering and customer success accelerators. They are
not compliance certifications, legal advice, or a replacement for assessor,
auditor, or change-management approval.
