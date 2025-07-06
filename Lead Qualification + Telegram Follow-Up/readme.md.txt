# 📊 Lead Qualification + Telegram Follow-Up (n8n Workflow)

This n8n workflow captures lead data via a webhook (e.g., from a form), checks whether the lead score exceeds a threshold (7), and if qualified, sends a Telegram notification and stores the lead details in a Google Sheet.

---

## ✅ Use Case

Automatically handle incoming leads:
- Qualify leads based on a score
- Notify your team on Telegram
- Store qualified leads in Google Sheets

---

## ⚙️ Workflow Overview

- **Trigger:** Webhook (receives JSON with lead info)
- **Logic:** Function + IF node to check if `score > 7`
- **Actions:**
  - Send Telegram alert to a predefined chat
  - Append qualified lead to Google Sheets

---

## 🧱 Workflow Steps

1. **Webhook Node**
   - Accepts POST requests with lead data (`name`, `email`, `score`)

2. **Function Node**
   - Evaluates whether the lead is qualified (`score > 7`)

3. **IF Node**
   - Branches logic based on qualification status

4. **Telegram Node**
   - Sends a message to your Telegram bot/chat if qualified

5. **Google Sheets Node**
   - Appends the lead details and timestamp to a sheet

---

## 📥 Sample Input (JSON)

```json
{
  "name": "Jane Doe",
  "email": "jane@example.com",
  "score": 9
}
