# Academic literature → UnitFlow feature and test traceability

This is a planning matrix connecting the FYP's selected related work to the **proposed MVP**, not a statement that research findings have been reproduced.

| Reference | Relevant UnitFlow module | Representative implementation | Proposed acceptance / evaluation |
| --- | --- | --- | --- |
| R1: Field-service AI/ML | Customer & Property 360 / Field Operations | Property-linked equipment records and technician job lifecycle | Service job retains correct customer, property and equipment links |
| R2: AI-enabled CRM | CRM / AI assistance | Extract a proposed service type, reported issue and desired date from an enquiry | Compare extracted fields against human-labeled examples |
| R3: AI-CRM literature review | Data model / customer experience | Connected customer contact history and follow-up information | User retrieves complete customer-to-job record without re-entering details |
| R4: Event-driven workflows | Workflow engine / SLA | Service request event → lead record → response timer → manager escalation → accepted estimate → job | Correct event sequence; recovery after restart; no duplicate job on repeated events |

## Cross-cutting constraints

### Tenant isolation
Every tenant-owned record must be scoped by an authenticated organization, with cross-tenant read/write rejection tests.

### Workflow consistency
- Store workflow versions, execution status and completion history.
- Support deterministic condition evaluation and persistent timers.
- Use duplicate-event detection/idempotency safeguards for retries and provider webhooks.
- Ensure estimate rejection does not create a service job.

### AI output safety
- AI extraction is a **suggestion**, not a diagnosis.
- Validate outputs against structured field constraints.
- Log changes and require review for sensitive data.

## Example end-to-end FYP scenario

1. Business owner logs in as a member of Tenant A.
2. An AC-repair enquiry creates a lead linked to a customer and property.
3. The system records a lead-response deadline and acknowledgement event.
4. If no human response is logged by the configured deadline, the manager alert branch runs.
5. Staff book an appointment and issue an estimate.
6. Acceptance of the estimate creates **one** linked service job.
7. Technician updates status, and an invoice record is stored.
8. AI proposes structured notes from the conversation; backend validation determines what may be saved.
9. Tests confirm Tenant B cannot access this journey's records.

Further requirements must be checked against the approved FYP scope and UnitZero's private product specification. See [paper comparisons](FOUR_PAPER_RESEARCH_GAPS.md).
