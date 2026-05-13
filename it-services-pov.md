# IT Services CSW POV Process

## Best Fit Customers

- Managed service providers
- SaaS companies
- Business process outsourcing providers
- Hosting and colocation providers
- Professional services firms with customer-facing platforms

## Common Business Drivers

- SOC 2 Type II evidence.
- ISO 27001 audit support.
- Customer due diligence.
- Tenant isolation proof.
- Ransomware blast-radius reduction.
- Production environment segmentation.
- Change drift detection.

## Recommended POV Scope

Pick one customer-facing service:

- Production SaaS application.
- Shared platform service.
- Customer tenant environment.
- Managed service control plane.
- Privileged access / jump host environment.
- CI/CD or deployment platform supporting production.

## Stakeholders

- CISO or head of security.
- CTO / platform engineering.
- SRE / operations.
- Application owner.
- Customer assurance / GRC.
- Internal audit.
- Customer success or sales engineering for due diligence reuse.

## Discovery Questions

- What system boundary is used for SOC 2 or ISO 27001?
- Which services are customer-facing and revenue-critical?
- How are tenants isolated today?
- Which workloads have privileged access to customer environments?
- What evidence do customers request during security reviews?
- What changed in the last audit period that was hard to prove?
- Which environments are production, staging, development, and shared services?

## Scope Pattern

```text
IT-Services
├── SOC2-System
│   ├── Production
│   ├── Supporting-Infra
│   ├── Admin-Access
│   └── Vendor-Integrations
├── Tenant-Isolation
│   ├── Tenant-A
│   ├── Tenant-B
│   └── Shared-Services
├── CI-CD
└── Monitoring-And-Logging
```

## Success Criteria

- Produce a live dependency map for the SOC 2 system boundary.
- Show tenant or customer environment segmentation evidence.
- Identify privileged access paths to production.
- Generate a candidate workload policy for the selected application.
- Create reusable evidence for customer security questionnaires.

## Evidence Package

- Production workload inventory.
- Tenant/shared-service communication map.
- Admin and management access path summary.
- External/vendor integration flow summary.
- ADM policy draft.
- Drift or unexpected flow findings.
- Audit-ready screenshots or exports for SOC 2 / ISO control owners.

## Cisco Products That Help

- Cisco Secure Workload for application dependency mapping and segmentation.
- Cisco ISE for admin access and campus/VPN context.
- Cisco Duo for privileged access MFA.
- Cisco Secure Firewall for perimeter and customer environment segmentation.
- Splunk for audit retention and evidence dashboards.
- Cisco XDR for investigation workflow.

## Common Outside Products

- Drata, Vanta, Secureframe, AuditBoard, ServiceNow GRC, or Archer for evidence management.
- Okta, Entra ID, Ping, SailPoint, or Saviynt for identity governance.
- Datadog, New Relic, or Prometheus/Grafana for service availability evidence.
- Wiz, Prisma Cloud, Lacework, Tenable, Qualys, or Rapid7 for cloud and vulnerability posture.

## Readout Narrative

"CSW helped the IT services team show customers and auditors that production workloads, tenant boundaries, privileged paths, and shared services are visible, explainable, and ready for least-privilege policy."
