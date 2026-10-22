# Security, privacy and compliance considerations

**Proposal stage:** These are safeguards we intend to design and test. This project **does not claim** existing compliance certifications, legal approvals, penetration-test results or deployed protections.

## Planned controls

| Topic | Planned approach |
| --- | --- |
| Tenant isolation | Scope every customer, property, job and automation event to its business/tenant; test cross-tenant access |
| Role-based access | Distinguish owner, sales representative, dispatcher and technician permissions |
| Authentication | Secure sign-in/session handling and server-side authorization checks |
| Transport | HTTPS for deployed application and provider webhooks |
| Integrations | Server-held API credentials, webhook signature verification and input validation |
| Customer privacy | Data minimization, controlled retention, limited access and appropriate customer consent |
| AI-assisted data | Validate extracted fields before CRM changes; don't turn customer suspicions into confirmed diagnoses |
| Workflow audit | Execution logs for troubleshooting with redaction of secrets and unnecessary personal information |

## Example

Company A and Company B use the same SaaS app. A salesperson from Company A must not be able to view Company B's customers, even by editing a URL or API request.

## Testing ideas

- Cross-tenant read/write denial on API endpoints.
- Permissions checks for technician vs owner.
- Invalid webhook-signature rejection.
- Duplicate-provider-event handling.
- Attempts to inject unexpected fields into AI extraction results.
- Checks that secrets and customer PII are absent from public logs.

Legal requirements depend on actual deployment regions, messaging/recording consent and provider contracts. Policies should be reviewed with supervisors before processing real customers' data.

## Publication policy

Never publish real customer details, credentials, call recordings, internal UnitZero paperwork or full proprietary source code in this public showcase repository.
