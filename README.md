# UnitFlow CRM — AI-Enabled Field Operations & Workflow Automation Web App (FYP)

> **Final Year Project (FYP) | Proposal & planning stage**  
> **Public project showcase — proprietary implementation is not published here**

**Official project title:** An AI-Enabled Web-Based CRM, Field Operations and Workflow Automation Platform for Home and Field Service Businesses.

UnitFlow is a proposed **multi-tenant, browser-based SaaS platform** for service businesses such as AC repair, plumbing and electrical companies. The goal is to connect customer enquiries, properties, estimates, technician jobs, communication and aftercare in one process.

## The idea in plain language

Imagine a customer requests AC repair at night. The company may miss the enquiry; later, staff may have to copy details between messaging apps, spreadsheets and job software. UnitFlow aims to connect those steps and help teams act on time.

**Planned customer journey:**  
`Enquiry → Lead → Appointment → Estimate → Accepted estimate → Job → Invoice → Aftercare`

## Planned FYP MVP

| Area | Proposed functionality |
| --- | --- |
| CRM | Customers, properties, equipment, leads and opportunities |
| Field operations | Appointments, estimates, technician assignments, jobs, invoice records |
| Communication | SMS, voice and email integrations |
| Workflow automation | Graph-based triggers, conditions, delays, retries, SLA alerts and logs |
| Platform | Business/tenant isolation, role-based permissions, mobile-responsive pages |
| Limited AI | Conversation summaries and validated extraction of CRM details |

## Proposed technology direction

- **Web app:** Next.js, React, TypeScript.
- **Data layer:** PostgreSQL + Prisma.
- **Background processing:** Redis/BullMQ plus a separately implemented workflow orchestrator.
- **Integrations:** Twilio, email provider and authenticated webhooks.
- **AI:** Pretrained language model for summaries and structured extraction; final model **not selected**.

*These are proposed technologies, not evidence of completed implementation.*

## Current progress (October 2026)

- FYP proposal and scoped product requirements documented.
- Industry context, competitor research and market charts prepared.
- Proposal-defence slides and presenter notes prepared.
- Conceptual customer-lifecycle, automation and architecture diagrams prepared.
- Security, privacy and compliance considerations outlined.
- **No working application, production integrations or measured test results are claimed yet.**

See [project status](docs/PROJECT_STATUS.md) and [development plan](docs/DEVELOPMENT_PLAN.md).

## Project team

- Ali Ahmed Khoso
- Arjia Ashraf

Academic supervisor: **Maj. Babar Yousaf**  
Industry supervisor: **Hilal Aziz (UnitZero)**

## Read the project

[Problem](docs/PROBLEM_STATEMENT.md) · [MVP Scope](docs/MVP_SCOPE.md) · [Workflow Example](docs/WORKFLOW_EXAMPLE.md) · [Architecture](docs/SYSTEM_ARCHITECTURE.md) · [Security](docs/SECURITY_AND_PRIVACY.md) · [Market Research](research/MARKET_AND_COMPETITORS.md) · [Roadmap](docs/DEVELOPMENT_PLAN.md)

## Public-repository notice

This repository is a **public progress showcase**, not the private application source repository. Do not publish credentials, customer records, private university/industry documents, call recordings, or proprietary implementation code here.

**No open-source license is granted.** All rights reserved by the applicable rights holders, subject to the team's and institution's intellectual-property agreements. Visibility on GitHub does not grant permission to reuse the material. Public files can still be viewed and copied technically.
