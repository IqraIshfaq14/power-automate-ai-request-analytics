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
