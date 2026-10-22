# Proposed system architecture

**Status:** Conceptual design for the FYP proposal. Nothing here establishes that a production service is running.

```text
Owners / sales reps / dispatchers / technicians
                      |
     Browser-based, mobile-responsive UI
          Next.js / React / TypeScript
                      |
     Application APIs, login and RBAC
               /      |       \
              /       |        \
    PostgreSQL     Workflow      AI assistance
    + Prisma       Orchestrator  summaries/extraction
    tenant data       |
                 Redis/BullMQ
              background workers
                      |
             Twilio / Email APIs
                      |
            Verified provider webhooks
                      |
              Application events
```

## Architecture decisions under consideration

- **Multi-tenancy:** Every customer and job belongs to an organization, and authenticated access is checked at the application/data layers.
- **Graph workflows:** Store nodes, edges, conditions, delays, definitions and versioned executions.
- **Event processing:** Domain events may start or advance workflows; workers handle delayed or retryable actions.
- **Persistence:** PostgreSQL stores CRM/operational records and durable workflow state. Redis/BullMQ is an execution queue, **not a complete workflow engine**.
- **Communication:** Provider APIs send messages; webhooks report replies, call events and delivery status.
- **AI:** A pretrained model may summarize communication and suggest structured fields; the backend validates accepted updates.

## Security and reliability concerns

Tenant isolation, signed webhooks, idempotency, secure credential handling, retries/backoff, execution logs and user permissions are core engineering tasks.

See [security principles](SECURITY_AND_PRIVACY.md) and [the example workflow](WORKFLOW_EXAMPLE.md).

## Open decisions

The final backend organization, deployment target, AI provider/model and service-provider configuration are pending supervisor review and testing.
