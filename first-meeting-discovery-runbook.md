# CSW First Meeting Discovery Runbook

## Purpose

This runbook helps a Cisco SA run the first customer discovery meeting for a Cisco Secure Workload POV. Use it to qualify the opportunity, identify the right POV scope, ask vertical-specific questions, and leave the meeting with clear next steps.

## Meeting Outcomes

By the end of the first meeting, the SA should know:

- The business driver for the POV.
- The customer vertical and regulatory pressure.
- The candidate application, environment, or regulated boundary.
- The technical owner, application owner, and executive sponsor.
- Whether CSW is being positioned for visibility, compliance evidence, microsegmentation, ransomware reduction, cloud migration, or policy enforcement.
- What data, access, and deployment prerequisites are needed for the next meeting.

## Suggested Agenda

| Time | Topic | Owner |
|---:|---|---|
| 0-5 min | Introductions and customer objective | Account team |
| 5-15 min | Business driver and current pain | Customer sponsor |
| 15-30 min | Application / environment discovery | SA |
| 30-45 min | Vertical-specific risk and compliance questions | SA + customer SMEs |
| 45-55 min | POV candidate scope and success criteria | SA |
| 55-60 min | Next steps, owners, and required inputs | Account team |

## Opening Script

"The goal today is not to design the full deployment. The goal is to pick the right first workload or environment where CSW can prove value quickly: visibility, dependency mapping, segmentation policy, risk reduction, and evidence. We will keep the first POV scoped tightly so the results are credible and actionable."

## Initial Discovery Questions

Use these questions before going into vertical-specific detail. The goal is to quickly determine whether the customer needs CSW for visibility, segmentation, compliance evidence, incident response, or enforcement.

### Customer Situation

- What prompted this meeting?
- What are you trying to improve: visibility, segmentation, compliance evidence, ransomware readiness, audit response, cloud migration, or application dependency mapping?
- Is there a deadline driving this work, such as an audit, board review, incident follow-up, renewal, migration, or regulatory milestone?
- Which business service or application would create the most value if we mapped and segmented it first?
- What is currently painful or manual about understanding workload communication?

### Current Visibility

- How do you know what talks to what today?
- Do application owners trust the current network diagrams?
- Do firewall rules or cloud security groups reflect the real application dependencies?
- Can you identify process-level communication, or only IP/port traffic?
- Can you quickly answer which workloads have high-risk ports, plaintext protocols, or unexpected internet egress?

### Current Segmentation

- Where is segmentation enforced today: firewall, VLAN, cloud security group, Kubernetes policy, host firewall, or manual rule review?
- Is the current model mostly north-south, east-west, or both?
- Which applications are over-permitted because nobody wants to break them?
- Which environment is safest for the first POV: lab, non-production, production monitoring only, or a bounded production app?
- What would need to be true before you would consider enforcement?

### Compliance and Risk

- Which framework matters most for this discussion: PCI, HIPAA, SOC 2, ISO 27001, NIST, CMMC, DORA, NIS2, NERC CIP, or internal policy?
- What evidence does the audit or risk team ask for repeatedly?
- What evidence is hard to produce today?
- Do you need proof of segmentation, proof of inventory, proof of policy operation, or proof of incident investigation?
- Are there crown-jewel applications, regulated data zones, or high-value assets we should prioritize?

### POV Readiness

- Can we get a representative workload list before kickoff?
- Can sensors be installed on the candidate workloads?
- Who approves sensor deployment and change windows?
- Are there cloud accounts, data centers, or operating systems we should exclude?
- Who should attend the POV kickoff: app owner, server team, network team, security operations, compliance, and change management?

## First Customer Demo Flow

Use this as a lightweight first-meeting demo path. Keep it short and outcome-oriented; do not turn the first meeting into a full product training session.

### Demo Setup

Before the meeting, prepare a demo tenant, screenshots, or recorded flow that shows:

- Workload inventory.
- Scope hierarchy.
- Application dependency map.
- Flow search.
- ADM-generated policy.
- Policy simulation or enforcement view.
- Vulnerability or high-risk communication context, if relevant.

### 15-Minute Demo Path

| Time | Demo step | Message |
|---:|---|---|
| 0-2 min | Show workload inventory | "CSW starts by making the workload estate visible, including owners, labels, OS, packages, and telemetry coverage." |
| 2-5 min | Show application scope | "We organize workloads around the business service or compliance boundary, not just subnets." |
| 5-8 min | Show observed flows | "This is the live dependency evidence: source, destination, port, protocol, process, and observed behavior." |
| 8-11 min | Show ADM policy | "CSW turns observed behavior into a policy candidate the app owner can review before enforcement." |
| 11-13 min | Show risk context | "The same view can highlight high-risk ports, plaintext protocols, unexpected egress, or vulnerable workloads." |
| 13-15 min | Show evidence output | "The POV output becomes an evidence package: inventory, flows, scope, policy candidate, exceptions, and expansion plan." |

### Demo Questions To Ask While Showing CSW

- Would your application owner recognize this dependency map?
- Which flow on this screen would be hardest for you to prove today?
- Which of these communications would you expect to be denied in a least-privilege model?
- Would this level of evidence help with your audit, incident response, or segmentation project?
- If we did this with one of your applications, which app should we start with?

### Demo Do's

- Keep the story focused on one application.
- Tie every screen to a customer pain.
- Use the customer's vertical language: CDE, ePHI, CUI, tenant, IBF, OT-facing IT, production boundary.
- Emphasize monitoring and simulation before enforcement.
- End by confirming the POV candidate scope.

### Demo Don'ts

- Do not promise instant enforcement.
- Do not imply CSW replaces firewalls, IAM, EDR, GRC, SIEM, or assessor judgment.
- Do not pick a scope so large that the POV becomes an enterprise deployment.
- Do not skip application owner validation.
- Do not demo every feature if the customer only cares about one outcome.

## Universal Discovery Questions

### Business Driver

- What triggered interest in Cisco Secure Workload now?
- Is this driven by audit, ransomware, cloud migration, segmentation, merger/acquisition, incident response, or application modernization?
- What problem is hardest to prove with your current tooling?
- What would make this POV worth expanding?
- Who will decide whether the POV is successful?

### Current Environment

- Which data centers, clouds, or regions are in scope?
- Which platforms matter most: VMware, bare metal, Windows, Linux, Kubernetes, AWS, Azure, GCP, or hybrid?
- Which applications are business critical?
- Which teams own the application, OS, network, cloud, security, and change process?
- Do you have a CMDB or authoritative workload inventory?

### Current Segmentation

- How is segmentation enforced today: firewall, VLAN, security group, NSG, Kubernetes policy, host firewall, or manual process?
- Are current network diagrams trusted?
- How often do firewall or security group rules drift from application reality?
- Which flows are known to be fragile or poorly documented?
- Are there applications where "nobody knows what talks to what"?

### CSW Readiness

- Can sensors be installed on the candidate workloads?
- Are there endpoint protection or change-control barriers?
- Can workloads reach a CSW SaaS tenant or cluster over required outbound connectivity?
- Are cloud connectors an option?
- What telemetry is acceptable during the POV: flow, process, package, vulnerability, forensics?
- Are there data handling, privacy, or retention concerns?

### POV Scoping

- Which one application would produce the clearest win?
- Can we cover all tiers: web, app, database, middleware, identity, monitoring, backup?
- Is non-production representative enough, or does production need to be included?
- What observation window captures normal application behavior?
- Which stakeholders must approve policy simulation or enforcement?

## Vertical-Specific Discovery

## Financial Services

### Customer Types

- Banking
- Insurance
- Fintech
- Payments
- Capital markets
- Financial SaaS

### Key Questions

- Which applications support payment, trading, banking, claims, or other important business functions?
- Are you trying to support DORA, PCI DSS, SWIFT CSCF, SOC 2, ISO 27001, or internal resilience goals?
- Which systems are CDE, CDE-connected, SWIFT-supporting, or production-critical?
- Which third parties or processors connect to the environment?
- Which application flows are required for settlement, payment processing, fraud, identity, or reporting?
- What segmentation evidence does audit or risk ask for today?
- Where are static diagrams or firewall rules least trusted?
- Which privileged access paths reach regulated workloads?

### Strong POV Candidates

- Payment processing application.
- Online banking service.
- SWIFT-supporting jump host or file transfer environment.
- Important Business Function under DORA.
- Customer-facing financial SaaS platform.

### Success Criteria Examples

- Prove current workload communication for one regulated financial application.
- Identify unexpected third-party or internet egress.
- Generate candidate least-privilege policy for a CDE or IBF application.
- Produce segmentation evidence for audit/risk review.

## Healthcare

### Customer Types

- Health systems
- Hospitals
- Clinics
- Payers
- Life sciences
- Business associates

### Key Questions

- Which applications store, process, transmit, or support ePHI?
- Is this POV tied to HIPAA, HITRUST, ransomware response, or clinical application visibility?
- Which systems are most critical to patient care?
- Which applications are hardest to patch or segment?
- Which flows matter most: EHR, PACS, HL7, billing, claims, identity, backup, monitoring?
- Which business associates or external partners communicate with ePHI systems?
- Which systems are clinical/biomedical adjacent but not good sensor candidates?
- What would privacy, compliance, or clinical leadership consider useful evidence?

### Strong POV Candidates

- EHR-supporting application.
- Billing or claims system.
- PACS or imaging support environment.
- HL7 integration engine.
- Clinical data warehouse.

### Success Criteria Examples

- Confirm ePHI workload boundary and communication paths.
- Identify unexpected access into ePHI systems.
- Identify plaintext or high-risk clinical communication.
- Produce a HIPAA/HITRUST-ready technical evidence package.

## IT Services and SaaS

### Customer Types

- Managed service providers
- SaaS companies
- Outsourcing providers
- Hosting providers
- Consulting and professional services firms

### Key Questions

- What is your SOC 2 or ISO 27001 system boundary?
- Which customer-facing services are in scope for audit or due diligence?
- How do you prove tenant isolation today?
- Which workloads have privileged access to customer environments?
- Which shared services support multiple customers or tenants?
- What evidence do customers request in questionnaires?
- Where has audit evidence been manual or painful?
- Which environments are production, staging, development, and shared services?

### Strong POV Candidates

- Production SaaS application.
- Customer tenant environment.
- Shared platform service.
- Managed service control plane.
- CI/CD service supporting production.

### Success Criteria Examples

- Produce a current dependency map for the SOC 2 system boundary.
- Show tenant/shared-service communication.
- Identify privileged access paths to production.
- Create reusable evidence for customer assurance.

## Retail and PCI

### Customer Types

- Retailers
- Ecommerce
- Restaurants and hospitality
- Franchise operators
- Payment service providers

### Key Questions

- What is currently in the CDE?
- Which systems are CDE-connected?
- Which systems are declared out of scope and why?
- Is the focus stores, ecommerce, POS, payment gateway, or back-end processing?
- Which third-party processors or gateways are involved?
- What diagrams or firewall reports does the QSA rely on today?
- Which payment flows are expected and which are unknown?
- Is scope reduction or segmentation validation the main goal?

### Strong POV Candidates

- Ecommerce checkout.
- Payment gateway service.
- POS back-end service.
- Store support service.
- Tokenization or HSM-adjacent workload set.

### Success Criteria Examples

- Produce a live CDE flow map.
- Identify CDE-to-out-of-scope communication.
- Generate candidate policy for one payment application.
- Create QSA-friendly segmentation evidence.

## Public Sector

### Customer Types

- Federal agencies
- State and local government
- Higher education
- Defense contractors
- Public-sector SaaS providers

### Key Questions

- What is the formal system boundary?
- Is this driven by NIST 800-53, FedRAMP, CMMC, Zero Trust, or ATO readiness?
- Which workloads process CUI, mission data, or high-value asset data?
- Which SSP components map to application, data, management, identity, and logging tiers?
- Which controls need better technical evidence?
- Which workloads are unsupported, unmanaged, or excluded?
- What evidence is needed for continuous monitoring or authorization?
- Who owns the SSP, POA&M, and control evidence?

### Strong POV Candidates

- FedRAMP moderate/high workload set.
- CUI enclave.
- Mission application.
- High-value asset.
- Identity or privileged access service.

### Success Criteria Examples

- Map CSW scopes to the system boundary.
- Produce workload evidence for selected AC, AU, CM, RA, SC, and SI controls.
- Identify segmentation gaps affecting ATO readiness.
- Build an expansion plan for continuous monitoring.

## Manufacturing and OT-Adjacent IT

### Customer Types

- Manufacturing
- Energy and utilities
- Pipeline operators
- Logistics and transportation
- Industrial companies

### Key Questions

- Which IT systems can affect OT availability or safety?
- Which systems bridge corporate IT and OT environments?
- Is the driver ransomware, NERC CIP, TSA, IEC 62443, or internal segmentation?
- Which jump hosts, patch repositories, identity systems, backup systems, historians, and vendor access systems support OT?
- Which workloads can safely run CSW sensors?
- Which assets require passive monitoring or compensating controls?
- Which vendors connect remotely, and through what systems?
- What maintenance windows or plant operations constraints apply?

### Strong POV Candidates

- OT-facing jump host environment.
- Patch repository.
- Backup service.
- Historian support servers.
- Vendor access service.
- Identity or PKI service supporting OT.

### Success Criteria Examples

- Map IT-side systems that support OT.
- Identify unexpected IT-to-OT or vendor access paths.
- Generate policy candidates for jump hosts or patch repositories.
- Clearly separate CSW-covered systems from OT-native controls.

## First Meeting Qualification Score

Use this quick score to decide whether to proceed.

| Signal | Green | Yellow | Red |
|---|---|---|---|
| Business driver | Clear pain and deadline | General interest | No clear problem |
| POV scope | One app or environment selected | Several candidates | Wants whole estate immediately |
| Ownership | Sponsor and technical owner identified | One owner missing | No accountable owner |
| Deployment path | Sensors/connectors feasible | Some change barriers | No deployment access |
| Success criteria | Measurable outcomes | Outcomes need refinement | No definition of success |
| Expansion potential | Clear next phase | Possible next phase | One-off curiosity |

## Required Follow-Up

After the first meeting, send a recap that includes:

- Business driver.
- Candidate POV scope.
- Vertical-specific compliance or risk driver.
- Named owners.
- Required technical inputs.
- Initial success criteria.
- Proposed timeline.
- Decision needed before kickoff.

## First Meeting Output Template

```text
Customer:
Vertical:
Business driver:
Primary framework / risk driver:
Candidate application or environment:
Known systems in scope:
Known systems out of scope:
Current segmentation method:
Expected observation window:
Success criteria:
Sponsor:
Technical owner:
Application owner:
Required prerequisites:
Risks / blockers:
Next meeting:
```
