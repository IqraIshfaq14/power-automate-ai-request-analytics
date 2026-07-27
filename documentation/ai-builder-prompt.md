## 🤖 AI Builder Prompt

### Purpose

The AI Builder Prompt converts unstructured business request emails into structured JSON that Power Automate can process automatically.

---

### Input

The prompt receives the cleaned email body as input.

**Example Email**

```text
Subject: VPN Access Request

Hello,

Our Finance department needs VPN access for two new employees before Monday.

Regards,
John
```

---

### Prompt Responsibilities

The prompt performs the following tasks:

- Classifies the request type
- Generates a concise business summary
- Recommends a priority level
- Detects customer sentiment
- Estimates business risk
- Calculates AI confidence
- Detects the email language
- Translates the summary into English if the email is written in another language
- Returns only valid JSON

---

### Expected JSON Output

```json
{
  "requestType": "Access Request",
  "summary": "Finance department requests VPN access for two new employees before Monday.",
  "priorityRecommendation": "High",
  "sentiment": "Neutral",
  "riskScore": 75,
  "confidenceScore": 93,
  "detectedLanguage": "English"
}
```

---

### Output Fields

| Field | Description |
|--------|-------------|
| requestType | AI classification of the request (Access Request, Incident, Service Request, Escalation, Unknown) |
| summary | Concise summary of the request |
| priorityRecommendation | AI-recommended priority (Low, Medium, High, Critical) |
| sentiment | Overall tone of the email |
| riskScore | Estimated business impact (0–100) |
| confidenceScore | AI confidence in the classification (0–100) |
| detectedLanguage | Language detected from the original email |

---

### Workflow Integration

```text
Incoming Email
      │
      ▼
Clean Email Body
      │
      ▼
AI Builder Prompt
      │
      ▼
Structured JSON
      │
      ▼
Parse JSON
      │
      ▼
Business Rules
      │
      ├── Duplicate Detection
      ├── Route Decision
      ├── SharePoint
      ├── Planner
      ├── Teams Notification
      └── Email Response
```

---

### Benefits

- Eliminates manual email reading
- Produces structured business data
- Supports multilingual requests
- Improves routing accuracy
- Enables AI-driven automation
- Integrates seamlessly with Power Automate
