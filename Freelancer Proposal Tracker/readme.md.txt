# Freelancer Proposal Tracker

An n8n automation workflow to track freelancer proposals using Notion and send daily reminders for pending ones.

## Workflow Steps

1. **Trigger**: Manual or scheduled trigger (e.g., Cron or Webhook).
2. **Notion**: Fetch proposals from a Notion database.
3. **Set Node**: Add today's date and simplify field names.
4. **Function Item**: Filter proposals that are not marked "Done" and are due today or earlier. Format deadline to a readable form like `Jul 1, 2025`.
5. **(Optional) Reminder**: Send filtered proposals to Slack, Telegram, or Email.

## Expected Notion Fields

- `property_title` – Proposal title
- `property_status` – Current status (e.g., Done, In Progress, Not started)
- `property_dead_line` – Proposal deadline

## Output Example

```json
{
  "title": "Test Proposal 1",
  "status": "Not started",
  "deadline": "Jul 1, 2025",
  "today": "2025-07-02"
}
