# Testing Scenarios

This document contains the main test cases used to validate the AI-powered request automation system.

## Test Case 1: Low Priority Request

**Purpose:** Verify backlog routing.

**Subject:** Low priority service request

```text
Request ID: REQ-2026-030
Customer: Contoso Ltd.
Priority: Low
Issue: Please add the finance dashboard shortcut to the user portal when possible.
Due Date: Next month
Stakeholders: Finance Team
```

## Expected Result

* **RouteDecision:** Backlog Queue
* **ProcessingStatus:** AI Processed
* Teams notification sent
* SharePoint item created

# Test Case 2: Medium Priority Request

## Purpose
Verify team assignment and Planner task creation.

## Request Details

- **Subject:** Medium reporting access request
- **Request ID:** REQ-2026-031
- **Customer:** Contoso Ltd.
- **Priority:** Medium
- **Issue:** Finance team needs reporting access for three new employees by next week.
- **Due Date:** Next week
- **Stakeholders:** Finance Department, IT Support

## Expected Result

- **RouteDecision:** Team Assignment
- Planner task created
- Teams notification sent
- SharePoint item updated with `PlannerTaskId`

# Test Case 3: High Priority Request

## Purpose
Verify approval workflow.

## Request Details

- **Subject:** High payroll access request
- **Request ID:** REQ-2026-032
- **Customer:** Contoso Ltd.
- **Priority:** High
- **Issue:** Payroll dashboard access is needed urgently for a finance manager.
- **Due Date:** Friday
- **Stakeholders:** Finance Manager, IT Manager

## Expected Result

- **RouteDecision:** Approval Required
- Approval request created
- ApprovalOutcome updated
- SharePoint item updated after approval or rejection

# Test Case 4: Critical Request

## Purpose
Verify immediate escalation.

## Request Details

- **Subject:** Critical payroll access outage
- **Request ID:** REQ-2026-033
- **Customer:** Contoso Ltd.
- **Priority:** Critical
- **Issue:** Payroll dashboard access is blocked for the whole finance department before payroll deadline.
- **Due Date:** Today
- **Stakeholders:** Finance Director, IT Manager

## Expected Result

- **RouteDecision:** Immediate Escalation
- **EscalationLevel:** Executive
- Urgent Teams notification sent
- SLA due date set to short timeframe

# Test Case 5: Manual Review

## Purpose
Verify low-confidence or unclear request handling.

## Request Details

- **Subject:** unclear request

### Message
Hello,  
Can someone check this thing for us?  
Thanks

## Expected Result

- **RouteDecision:** Manual Review
- **ProcessingStatus:** Manual Review
- Manual review Teams notification sent

# Test Case 6: Duplicate Request

## Purpose
Verify duplicate detection.

## Request Details

> Send the same Request ID twice.

- **Request ID:** REQ-2026-033
- **Customer:** Contoso Ltd.
- **Priority:** Critical
- **Issue:** Duplicate test request.
- **Due Date:** Today
- **Stakeholders:** Finance Director, IT Manager

## Expected Result

- **DuplicateStatus:** Duplicate
- **RouteDecision:** Manual Review
- Duplicate notification sent
- Request flagged for review

# Test Case 7: Multi-Language Request

## Purpose
Verify language detection and English summary.

## Request Details

- **Subject:** Solicitud urgente de acceso
- **ID de solicitud:** REQ-2026-050
- **Cliente:** Contoso Ltd.
- **Prioridad:** Alta
- **Problema:** El equipo de finanzas necesita acceso urgente al panel de nómina.
- **Fecha límite:** Hoy
- **Interesados:** Director de Finanzas, Gerente de TI

## Expected Result

- **DetectedLanguage:** Spanish
- AI summary generated in English
- Request classified correctly
- SharePoint item created



