# Example workflow: enquiry → service job

This is a **planned flow**, not a claim of a deployed workflow engine.

## Scenario

A homeowner sends an AC repair request while the office is closed. The system should help the business acknowledge it, assign responsibility, track response time and move the resulting service work forward.

```text
New service request
       |
Create lead and record tenant-scoped event
       |
Assign salesperson + request acknowledgement SMS
       |
Start configured response-time (SLA) timer
       |
Did staff respond by the deadline?
       |                 |
      YES                NO
       |                 |
Continue sales       Alert manager
       |                 |
       +------ follow-up-+
                  |
           Book appointment
                  |
           Prepare estimate
                  |
       Estimate accepted?
         |           |
        YES          NO → follow-up / close
         |
       Create linked service job
         |
      Technician update → invoice → aftercare
```

## Execution-engine responsibilities

- Persist workflow definitions and versions.
- Store each run's current node, status and timestamps.
- Evaluate conditions and execute delayed actions through background workers.
- Use idempotency keys for repeat webhooks/retries to avoid duplicate jobs or messages.
- Record failures, controlled retries and observable execution history.
- Verify tenant authorization for every automated read/write operation.

## Scenarios to test

| Test case | Expected behavior |
| --- | --- |
| Salesperson replies before deadline | No missed-response escalation |
| No reply before deadline | Manager notification requested |
| Duplicate service-request webhook | No duplicate lead/job |
| Messaging provider temporarily unavailable | Tracked error and safe retry/fallback |
| Estimate rejected | Do not create a service job |
| Workflow worker restarts during delay | Persisted workflow can resume |

The configured SLA duration, provider accounts and retry policy will be selected during implementation.
