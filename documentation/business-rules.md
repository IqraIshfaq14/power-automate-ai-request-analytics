# Business Rules

This document describes the routing and validation rules used in the AI-powered request automation flow.

## Request Categories

AI Builder classifies each request into one of the following categories:

| Category | Description |
|---|---|
| Access Request | Request for access to a system, dashboard, file, or application |
| Incident | Issue, outage, error, or service disruption |
| Service Request | General support or service request |
| Escalation | Request requiring urgent or higher-level attention |
| Unknown | Request cannot be confidently classified |

## Priority Levels

| Priority | Description |
|---|---|
| Low | Non-urgent request with flexible timeline |
| Medium | Standard request requiring team assignment |
| High | Important request requiring approval or manager visibility |
| Critical | Urgent business-impacting issue requiring immediate escalation |
| Unknown | Priority cannot be determined |

## Routing Logic

| Condition | Route Decision |
|---|---|
| AI confidence below 60 | Manual Review |
| Request type is Unknown | Manual Review |
| Priority is Low | Backlog Queue |
| Priority is Medium | Team Assignment |
| Priority is High | Approval Required |
| Priority is Critical | Immediate Escalation |

## Conditional Processing

| Route Decision | Processing Action |
|---|---|
| Backlog Queue | Store request and notify team in Teams |
| Team Assignment | Create Planner task and notify team |
| Approval Required | Start approval workflow and update SharePoint based on outcome |
| Immediate Escalation | Send urgent Teams notification and mark as escalated |
| Manual Review | Notify reviewers for human validation |

## SLA Rules

| Route Decision | SLA Target |
|---|---|
| Manual Review | 1 day |
| Backlog Queue | 14 days |
| Team Assignment | 5 days |
| Approval Required | 2 days |
| Immediate Escalation | 4 hours |

## Duplicate Detection

If a new request has the same Request ID as an existing SharePoint item, it is flagged as a duplicate and routed to manual review.

## Approval Rules

High-priority requests require approval before moving forward.

Approval outcomes:

- Approved
- Rejected
- Pending
- Not Required

## Escalation Rules

Critical requests are marked with executive-level escalation and trigger urgent notification.

## Manual Review Rules

Requests are routed to manual review when:

- AI confidence is low
- Request type is Unknown
- Required fields are missing
- Duplicate request is detected
