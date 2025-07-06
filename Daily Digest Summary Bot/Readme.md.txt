# 📊 Daily Digest Summary Bot (n8n)

This workflow runs every day at 6 PM and automatically:
- Pulls all records from Airtable (e.g., tasks, updates)
- Summarizes them with OpenAI
- Posts the result to a Slack channel

## 🔧 Workflow Steps

1. **Cron Trigger**: Fires daily at 6:00 PM
2. **Airtable Node**: Fetches all tasks/entries
3. **Function Node** *(optional)*: Formats text into bullet points
4. **OpenAI Node**: Converts data into a clear summary
5. **Slack Node**: Posts summary to `#daily-updates` or chosen channel

## 📚 Example Summary Sent to Slack


## 🔐 Credentials Required

- Airtable API Key (or OAuth)
- OpenAI API Key
- Slack Bot Token (w/ `chat:write` permission)

## 🔁 Customization Ideas

- Filter only today's records in Airtable
- Include top priority tasks or bugs
- Include deadline reminders
- Send different summaries to different teams

## 🤖 Built With

- n8n (Self-hosted or Cloud)
- Airtable
- OpenAI (ChatGPT or Claude)
- Slack

---


