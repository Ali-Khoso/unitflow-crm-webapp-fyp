# Database Schema Design Checklist

**Status:** Planning document for UnitFlow CRM Web App FYP. The Prisma schema is still a placeholder. This document does not claim that any database tables, migrations, or application code are complete.

## Planned data areas

| Domain | Example concepts to design | Why it matters |
| --- | --- | --- |
| Organization & access | Business/tenant, user, role, membership | Keep each service company's data separate |
| Customer & property | Contact, customer, property, equipment | Connect a person to their service locations and assets |
| Sales | Lead, opportunity, appointment, estimate | Track enquiry-to-booking progression |
| Field operations | Service job, technician assignment, invoice | Connect approved work to service delivery |
| Communication | Message/call event, communication log | Preserve customer follow-up context |
| Workflow automation | Workflow definition, version, execution, step/event log | Support triggers, delays, conditions and troubleshooting |

**These are proposed entities, not finalized Prisma model names.**

## Before writing `schema.prisma`

1. Confirm MVP requirements and the minimum end-to-end AC-repair scenario with supervisors.
2. Identify which records belong to a tenant; apply tenant ownership and authorization checks consistently.
3. Define relationships between customer, property, equipment, lead, estimate and service job.
4. Specify unique constraints, foreign keys, indexes and relevant lifecycle statuses.
5. Design workflow definitions and individual execution records separately, including retry and idempotency metadata.
6. Decide how to represent users who belong to one or more organizations.
7. Review privacy, retention and audit needs for communications and AI-generated suggestions.
8. Review the schema before creating migrations or seed data.

## Example acceptance questions

- Can two businesses store similar customer names without seeing each other's data?
- Does every service job point to the appropriate customer/property and accepted estimate?
- Can a failed or restarted workflow be resumed without duplicate jobs or messages?
- Can a technician see only permitted assignments?
- Can an AI-extracted field be reviewed before it changes a customer record?

## Security and publishing

This public repository contains high-level planning only. Do not commit production credentials, customer information, internal UnitZero materials, database dumps or proprietary implementation code.

**Next step:** Add actual models and relations to [`prisma/schema.prisma`](../prisma/schema.prisma) after the team shares and approves the schema.
