# Solution Architecture

This document describes the high-level architecture of the AI-powered request automation and analytics system.

## Architecture Flow

```text
Incoming Email
     ↓
Outlook Trigger
     ↓
Power Automate Cloud Flow
     ↓
Keyword Filtering
     ↓
HTML-to-Text Conversion
     ↓
Field Extraction
     ↓
AI Builder Classification and Summarization
     ↓
Validation and Business Rules
     ↓
Dynamic Routing
     ↓
SharePoint Tracking List
     ↓
Teams / Planner / Approvals / Escalations
     ↓
Analytics-Ready Dataset
```

# Main Components

| Component | Purpose |
|---|---|
| **Outlook** | Receives incoming request emails |
| **Power Automate** | Orchestrates the full automation process |
| **HTML-to-Text** | Converts email body into clean text |
| **Expressions** | Extract structured fields from email content |
| **AI Builder** | Classifies, summarizes, and scores requests |
| **SharePoint List** | Stores request records and audit data |
| **Teams** | Sends notifications and escalation alerts |
| **Planner** | Creates team assignment tasks |
| **Approvals** | Handles approval-required requests |
| **Power BI** | Optional analytics and dashboard layer |

# Data Flow Summary

1. A request email arrives in **Outlook**.
2. **Power Automate** checks whether the email is relevant.
3. The email body is converted from HTML to plain text.
4. Key fields are extracted from the body.
5. **AI Builder** classifies and summarizes the request.
6. Business rules determine the route decision.
7. Request data is stored in **SharePoint**.
8. **Teams**, **Planner**, and **Approvals** are triggered based on the route decision.
9. The structured SharePoint data can be used for analytics and reporting.

# Analytics Layer

The SharePoint list acts as the operational data source for analytics.

## Example Analytics Use Cases

- Request volume trends
- SLA performance tracking
- Priority distribution
- Escalation monitoring
- Approval outcome analysis
- Duplicate request monitoring
- AI confidence score tracking
