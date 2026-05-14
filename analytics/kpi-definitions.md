# KPI Definitions

This project converts unstructured request emails into structured data that can be analyzed for operational insights.

## Core KPIs

| KPI | Description |
|---|---|
| Total Requests | Total number of requests received |
| Open Requests | Requests not yet resolved |
| Resolved Requests | Requests marked as completed or resolved |
| Requests by Priority | Distribution of Low, Medium, High, and Critical requests |
| Requests by Type | Distribution of Access Request, Incident, Service Request, Escalation, and Unknown |
| Manual Review Rate | Percentage of requests routed to manual review |
| Approval Rate | Percentage of approval-required requests that were approved |
| Rejection Rate | Percentage of approval-required requests that were rejected |
| Escalation Rate | Percentage of requests escalated to manager or executive level |
| Duplicate Request Rate | Percentage of requests flagged as duplicates |
| SLA Breach Rate | Percentage of requests that passed the SLA due date |
| Average Risk Score | Average AI-generated risk score |
| Average AI Confidence Score | Average confidence score from AI classification |

## Example Calculations

### Manual Review Rate

```text
Manual Review Requests / Total Requests
