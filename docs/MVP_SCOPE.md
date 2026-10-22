# FYP MVP scope

The target is a **functional lead-to-invoice demonstration**, not a production-ready replacement for enterprise platforms.

## Included in the proposed FYP

| Module | Planned capabilities |
| --- | --- |
| Accounts and organizations | Multiple businesses, isolation of tenant records, role-based access |
| CRM and property history | Contacts, customers, properties, equipment, leads/opportunities |
| Sales workflow | Appointment booking, estimates, estimate-acceptance transition |
| Field operations | Service jobs, technician assignment, updates, invoice records |
| Messaging | SMS/voice/email integrations and logged communication events |
| Automation | Visual workflow graph; triggers, conditions, delays, actions, SLA timers, retries and execution logs |
| Basic reporting | Leads, jobs, response-time and operational overview |
| AI-assisted records | Conversation summaries and structured extraction with validation |
| Quality | Integration tests, security checks, latency/reliability/accuracy/usability evaluation |

## Planned end-to-end acceptance scenario

1. Submit a simulated AC repair enquiry.
2. Create and assign a lead.
3. Acknowledge the request and start a response deadline.
4. Confirm a timely follow-up or trigger manager escalation.
5. Schedule an appointment and produce an estimate.
6. **Only after estimate acceptance**, create the service job.
7. Record technician progress and an invoice.
8. Review the linked customer/property history and workflow execution log.

## Explicitly deferred

- Integrated online payments and full accounting.
- Advanced technician route optimization.
- Meta social-media integrations.
- Autonomous AI agents.
- Marketplace/enterprise ecosystem.

## Scope guardrails

- Multi-company data isolation is mandatory even in the demo.
- AI outputs must be validated; they should not silently become confirmed diagnoses.
- Demo use cases and measurable thresholds must be approved with supervisors.
- Future product ambitions should not be misrepresented as completed FYP deliverables.
