# MVP scope: agent-assisted complaints and CAPA

Note: this is an uncontrolled planning document. The hosting region, technology stack, identity provider, and job queue it lists as open were decided in DS-001.

Draft v0.1, October 2026. Segment, pricing, and acceptance targets are hypotheses to test with design partners.

## Who it is for

Small medical device companies, roughly 5 to 50 people, with no dedicated quality software. They run complaints and CAPA on spreadsheets, email, and shared drives. First target: small software and AI device makers, to be confirmed after customer interviews. Hardware makers can use the same modules later.

## The problem

Complaints and CAPAs are daily work, but the records are scattered, slow to assemble for an audit, and easy to lose track of. Reportability decisions and root cause work are the slowest, most error-prone steps.

## What is in the MVP

- **Complaint handling:** intake by form or forwarded email, awareness date, structured record, status workflow, similar-complaint lookup

- **Triage agent:** proposes classification, severity, reportability, and missing information, with citations, for a reviewer to approve (see the triage agent spec)

- **Reportability support:** urgent flags and deadline countdowns, with report fields captured but no submission to regulators

- **Nonconformance reports (simple):** create, disposition, and link to a CAPA

- **CAPA:** problem statement, root cause, actions with owners and due dates, effectiveness check, closure approval, and links back to complaints and NCRs

- **Foundation:** user roles, e-signatures with a stated meaning, audit trail, record versioning, separation of each company's data, and PDF or CSV export for audits

- **Reference library:** upload approved procedures so the agent can cite them (read-only, not full document control)

- **Validation package for the tool:** intended use, requirements, and a test summary customers can show an auditor

## What is out of the MVP

- Document control and training records

- Risk management and FMEA

- Process and product monitoring

- Change control and supplier management

- GitHub and Jira traceability

- Report submission to regulators

- A custom form builder

- Equipment integrations, mobile app, single sign-on, multiple languages

## Success criteria

- Two to three design partner companies handle real complaints in it

- Time from receipt to a signed triage decision is shorter than their current process, measured against a baseline

- No missed urgent flags in the validation test set

- A customer can pull a full complaint-to-CAPA trail for a mock audit in minutes

- At least one customer is willing to pay

## Pricing hypothesis

A flat monthly price per company, tiered by user count, starting low. Set no numbers until design partners react. Offer a free pilot in exchange for feedback and a case study.

## Build order

1. Foundation: accounts, roles, audit trail, e-signature
2. Complaint record and workflow
3. CAPA and NCR, with links between them
4. Triage agent and review screen
5. Reference library and validation package
6. Design partner pilots

## Risks to watch

- Scope creep into a form builder or a full eQMS

- Security and validation questions from customers before they will trust a new system

- Agent accuracy on reportability, which is why the agent stays conservative and a person decides

- Limited time while working full-time and finishing school

- Employment agreement terms on outside work, which should be checked before taking customers

## Open decisions

- Target segment: software and AI devices only, or all small device makers

- US rules only, or EU as well

- Hosting region and technology stack

- Whether to offer a paid service package alongside the software for early customers
