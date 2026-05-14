
# AI-Powered Request Automation and Analytics System

## Project Overview

This project is an enterprise-style request processing system built with Microsoft Power Automate, AI Builder, SharePoint, Microsoft Teams, Planner, Outlook, and Approvals.

The solution monitors incoming emails, extracts structured and semi-structured request information, uses AI to classify and summarize requests, applies business rules, routes requests dynamically, stores the results, and supports approvals, escalations, SLA tracking, duplicate detection, and analytics.

## Business Problem

Organizations often receive business and service requests through inconsistent email formats. Manual triage can be slow, error-prone, and difficult to track.

This project automates request intake and converts unstructured email content into structured, analytics-ready data.

## Key Features

- Outlook email intake
- Keyword-based filtering
- HTML-to-text conversion
- Structured field parsing
- AI Builder classification and summarization
- Priority recommendation
- Sentiment analysis
- Risk score and confidence score
- Business rule validation
- Dynamic routing
- SharePoint request tracking
- Teams notifications
- Planner task creation
- Approval workflows
- Escalation handling
- SLA tracking
- Duplicate detection
- Auto-response email
- Multi-language support
- Audit logging
- Manual review queue
- AI feedback loop

## Tools Used

- Microsoft Power Automate
- AI Builder
- SharePoint Lists
- Microsoft Teams
- Microsoft Planner
- Outlook
- Approvals
- Power BI-ready data model

## Solution Architecture

Email → Power Automate → HTML-to-Text → Parsing Logic → AI Builder → Routing Logic → SharePoint → Teams / Planner / Approvals → Analytics

## Data Analytics Relevance

This project converts unstructured email requests into structured operational data. The captured data can be used for analytics such as request volume, request categories, SLA performance, priority distribution, approval outcomes, escalation rates, duplicate requests, risk score trends, and AI confidence monitoring.

## Example KPIs

- Total requests received
- Requests by category
- Requests by priority
- Requests by customer
- Average AI confidence score
- Average risk score
- Manual review percentage
- Approval rate
- Escalation rate
- Duplicate request rate
- SLA breach rate
- Open vs resolved requests

## Workflow Summary

1. Monitor incoming emails.
2. Filter relevant request emails.
3. Convert email body from HTML to plain text.
4. Extract structured fields such as Request ID, Customer, Priority, Description, and Stakeholders.
5. Use AI Builder to classify and summarize the request.
6. Generate confidence score, risk score, sentiment, and priority recommendation.
7. Apply routing rules.
8. Store request information in SharePoint.
9. Notify Teams, create Planner tasks, trigger approvals, or escalate depending on the route.
10. Track SLA, duplicate status, audit history, and final resolution.

## Sample Request

```text
Request ID: REQ-2026-019
Customer: Contoso Ltd.
Priority: High
Issue: User access to payroll dashboard required urgently.
Due Date: Friday
Stakeholders: Finance Department, IT Manager
