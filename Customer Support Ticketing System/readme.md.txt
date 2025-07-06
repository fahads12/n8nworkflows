# 📩 Customer Support Ticketing System (n8n + Gmail + Trello/Notion + Slack)

This n8n automation workflow creates a lightweight but powerful customer support system. It listens for incoming support emails via Gmail, creates a ticket in Trello or Notion, and sends a real-time Slack alert to your support team.

---

## 🧭 Workflow Summary

| Component       | Purpose                                              |
|------------------|------------------------------------------------------|
| **Gmail Trigger**| Captures incoming emails in real time               |
| **Set/Function** | Parses email details (subject, body, sender)        |
| **Trello/Notion**| Creates a support ticket or issue card              |
| **Slack Node**   | Notifies team of new issue                          |
| **IF/Error Node**| Detects missing info or processing failures         |

---

## 🔧 Tools Used

| Tool        | Purpose                           |
|-------------|-----------------------------------|
| Gmail       | Triggering on new support emails  |
| Trello/Notion | Storing the ticket or task        |
| Slack       | Notifying support team            |
| n8n         | Workflow engine                   |

---

## 🚀 How It Works

1. **Gmail Trigger Node**
   - Watches the `INBOX` for new messages
   - Trigger mode: `Message Received`
   - Uses OAuth2 for authentication
   - Filters can be added to only trigger on emails with keywords like "Support", "Help", "Issue"

2. **Set or Function Node**
   - Parses:
     - Sender’s email address
     - Subject (used as ticket title)
     - Body text (used as ticket description)

3. **Trello or Notion Node**
   - **Trello**:
     - Adds a card to “Support Tickets” list
     - Fields: `Title`, `Description`, `Labels`
   - **Notion**:
     - Creates a new page in the support database
     - Maps fields like `Email`, `Title`, `Description`, `Status`

4. **Slack Node**
   - Sends a message to the support Slack channel
   - Includes sender, subject, and preview of message

5. **IF Node (Optional)**
   - Checks for missing data (like blank subject)
   - Sends fallback Slack alert if something goes wrong

---

## ✨ Optional Features

- 🧪 Add `Google Sheets` or `Airtable` logging for records
- ✍️ Auto-reply to sender via Gmail node: “Thanks, we received your issue”
- 📥 Attach email attachments to ticket (advanced setup)
- 🎫 Assign tickets to specific team members

---

## 🔐 Credentials Required

| Node         | Auth Method         |
|--------------|---------------------|
| Gmail        | OAuth2 (Secure Login) |
| Slack        | OAuth or Webhook URL |
| Trello       | API Key + Token      |
| Notion       | Integration Token    |

---

## 🛡️ Error Handling Strategy

- ❗ IF node checks if `subject` or `body` is empty
- ❗ If invalid, Slack is notified with a fallback error
- ✅ Prevents workflow crashes on malformed emails

---

## 📝 Example Slack Message

```text
📩 New Support Ticket

*From:* support@customer.com  
*Subject:* Login issue on dashboard  
*Message:* I'm unable to log in with my credentials...
