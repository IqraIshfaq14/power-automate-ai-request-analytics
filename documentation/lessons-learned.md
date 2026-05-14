# Lessons Learned

This project helped demonstrate how automation, AI, and analytics can work together in a real business process.

## Key Learnings

- Power Automate can process both structured and semi-structured email requests.
- HTML email bodies need to be converted into plain text before parsing.
- Variables make expressions easier to manage and reduce action reference errors.
- AI Builder can classify and summarize request content.
- Confidence scoring is important for deciding when human review is needed.
- SharePoint can act as a lightweight tracking database.
- Teams, Planner, and Approvals can be combined to support business process orchestration.
- Audit logging improves traceability.
- SLA dates make the process easier to monitor.
- Structured request data can support Power BI dashboards and operational analytics.

## Challenges Faced

- Handling inconsistent email formats
- Managing Power Automate expression syntax
- Referencing action outputs correctly
- Cleaning HTML email content
- Designing routing logic
- Tracking approval and escalation states
- Creating analytics-ready data fields

## Improvements for the Future

- Build a Power BI dashboard
- Move storage from SharePoint to Dataverse
- Use Azure OpenAI for more advanced AI processing
- Add Adaptive Cards for manual review
- Add role-based approval rules
- Improve duplicate matching using fuzzy logic
- Add automated SLA breach prediction
- Add a feedback loop to improve AI classification quality
