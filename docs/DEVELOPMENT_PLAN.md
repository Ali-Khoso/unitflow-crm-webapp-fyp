# Development roadmap and planned evaluation

**Proposed methodology:** Agile / iterative and incremental development. This is a planning approach, not a statement that the phases have been implemented.

## Phases

| Phase | Target output | Important verification |
| --- | --- | --- |
| 1. Foundation | Organizations, login, authorization, DB schema | Cross-tenant isolation checks |
| 2. CRM core | Customers, properties, equipment, leads, pipeline | Data integrity and role permissions |
| 3. Communication | SMS/call/email integration, inbound webhooks | Provider signature and event handling |
| 4. Field operations | Appointments, estimates, jobs, technician view, invoices | Lead-to-invoice integration tests |
| 5. Automation and AI | Workflow graph execution, timers, retry policy, extraction | Reliability and labeled extraction tests |
| 6. Evaluation/deployment | Demo environment, test results, usability report, documentation | End-to-end acceptance scenarios |

**Schedule:** Dates/durations must be aligned with the university's FYP calendar. No fabricated completion dates are listed.

## Planned academic measurements

- **Workflow reliability:** fraction of test scenarios executing the intended sequence correctly.
- **Event-processing latency:** elapsed time from event arrival to relevant action being scheduled or completed, reported with clear definitions.
- **AI extraction quality:** accuracy of extracted fields against a manually labeled test set; track incorrect or missing fields.
- **User task efficiency:** completion time, errors and user feedback for representative tasks.
- **Security validation:** tenant-crossing/API permission tests and webhook authentication checks.

We have **not yet collected baseline results, validated quantitative improvements or final performance numbers**.

## Team feasibility and risk considerations

Three-person FYP: prioritize one end-to-end AC repair case before advanced features. Use staged integrations or test environments if live provider accounts are not available.

Risks include scope creep, external API account/budget restrictions, timer/retry complexity, cross-tenant data exposure, AI extraction mistakes and schedule pressure.

Mitigations: enforce the MVP boundary, keep integration interfaces modular, test duplicate/retry cases, validate AI suggestions and obtain regular supervisor review.

## Deliverables planned

Runnable source code **in an authorized private development repository**, working demo, tests, final report, architecture documentation and evaluation results. Individual member responsibilities remain subject to team agreement.
