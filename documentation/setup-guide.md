# Setup Guide

This guide explains the high-level setup process for the AI-powered request automation and analytics system.

## Prerequisites

- Microsoft 365 account
- Power Automate access
- SharePoint site
- AI Builder access
- Microsoft Teams
- Microsoft Planner
- Outlook mailbox
- Approvals connector access

## Step 1: Create SharePoint List

Create a SharePoint list named:

```text
AI Request Intake
```
## Recommended Columns

| Column | Type |
|---|---|
| RequestID | Single line of text |
| Customer | Single line of text |
| RequestType | Choice |
| Priority | Choice |
| DueDate | Date and time |
| Description | Multiple lines of text |
| Stakeholders | Multiple lines of text |
| OriginalEmailBody | Multiple lines of text |
| OriginalSender | Single line of text |
| EmailReceivedTime | Date and time |
| ProcessingStatus | Choice |
| AISummary | Multiple lines of text |
| AIConfidenceScore | Number |
| RiskScore | Number |
| ApprovalHistory | Multiple lines of text |
| FinalResolutionState | Choice |
| RouteDecision | Choice |
| SLADueDate | Date and time |
| PlannerTaskId | Single line of text |
| ApprovalOutcome | Choice |
| EscalationLevel | Choice |
| ErrorMessage | Multiple lines of text |
| LastUpdatedByFlow | Date and time |
| AuditLog | Multiple lines of text |
| DuplicateStatus | Choice |
| DuplicateOfRequestID | Single line of text |
| DetectedLanguage | Single line of text |

## Step 2: Create Power Automate Flow

Create an automated cloud flow using:

```text
Office 365 Outlook - When a new email arrives (V3)
```
The flow monitors incoming emails and filters relevant business requests.

## Step 3: Convert Email Body

Use:

```text
Content Conversion - Html to text
```
Store the clean output in a string variable:

```text
varCleanBody
```

## Step 4: Extract Request Fields

Use Power Automate expressions to extract the following fields:

| Field | Description |
|---|---|
| Request ID | Unique request identifier |
| Customer | Customer or department name |
| Priority | Low, Medium, High, Critical, or Unknown |
| Description | Main issue or request details |
| Stakeholders | People or teams involved |

## Step 5: Add AI Builder

Use AI Builder to classify, summarize, and score the incoming request.

| AI Output | Purpose |
|---|---|
| Request Type | Classifies the request as Access Request, Incident, Service Request, Escalation, or Unknown |
| Summary | Creates a short summary of the request |
| Priority Recommendation | Suggests Low, Medium, High, Critical, or Unknown |
| Sentiment | Detects tone such as Neutral, Urgent, Frustrated, or Unknown |
| Risk Score | Scores business risk from 0 to 100 |
| Confidence Score | Scores AI confidence from 0 to 100 |
| Detected Language | Identifies the language of the email |

## Step 6: Apply Business Rules

Use conditions and switch controls to route requests based on priority, AI confidence, request type, and business rules.

| Route Decision | Action |
|---|---|
| Backlog Queue | Teams notification |
| Team Assignment | Planner task |
| Approval Required | Approval process |
| Immediate Escalation | Urgent Teams alert |
| Manual Review | Manual review queue |

## Step 7: Store and Track Results

Create or update SharePoint items with parsed values, AI results, route decision, SLA due date, approval outcome, audit log, and final status.

Tracked values include:

- Parsed request fields
- AI classification results
- Route decision
- SLA due date
- Approval outcome
- Escalation level
- Duplicate status
- Audit log
- Final resolution state

## Step 8: Advanced Features

Optional enterprise enhancements include:

- Duplicate request detection
- Auto-response email
- Multi-language support
- SLA monitoring flow
- AI feedback loop
- Security-based approvals
- Scope-based error handling
