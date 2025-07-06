# 📇 Typeform to CRM Lead Logger – n8n Workflow

This n8n workflow captures new lead submissions from a Typeform form, logs them into a Google Sheet (acting as a CRM), and sends an instant alert to Slack for the sales or support team.

---

## 🚀 Workflow Overview

1. **Typeform** – Collects lead information  
2. **Webhook (n8n)** – Receives the form submission  
3. **Google Sheets** – Logs lead into CRM sheet  
4. **Slack** – Notifies the relevant team

---

## 🧩 Nodes Used

- 🔗 Webhook
- 📄 Google Sheets
- 💬 Slack

---

## 📥 Step 1: Typeform Setup

Build your form with common lead fields such as:

- Full Name (short text)
- Email Address
- Company Name
- Phone Number
- Service Interested In
- Comments or Message

➡️ Go to **Typeform > Connect > Webhooks** and add your webhook URL:


Submit a test form so n8n captures the structure.

---

## 🌐 Step 2: n8n Workflow

### 🔹 Webhook Node

- **Method**: `POST`  
- **Path**: `new-lead`  
- Captures data submitted via Typeform.

---

### 🔹 Google Sheets Node – Append Row

Logs the lead info into your Google Sheet CRM:

| Column              | Value (Mapped from Typeform)               |
|---------------------|--------------------------------------------|
| Timestamp           | `{{ $now }}`                               |
| Full Name           | `{{$json.form_response.answers[0].text}}`  |
| Email               | `{{$json.form_response.answers[1].email}}` |
| Company             | `{{$json.form_response.answers[2].text}}`  |
| Phone               | `{{$json.form_response.answers[3].text}}`  |
| Service Interested  | `{{$json.form_response.answers[4].text}}`  |
| Message             | `{{$json.form_response.answers[5].text}}`  |

> Make sure your Google Sheet has these columns in the same order.

---

### 🔹 Slack Node – Send Alert

Sends a message to your Slack channel (e.g., `#sales-leads`):

**Example Message:**
```markdown
🚀 New Lead Submitted

👤 Name: {{$json.form_response.answers[0].text}}  
📧 Email: {{$json.form_response.answers[1].email}}  
🏢 Company: {{$json.form_response.answers[2].text}}  
📞 Phone: {{$json.form_response.answers[3].text}}  
🎯 Interested In: {{$json.form_response.answers[4].text}}  
📝 Message: {{$json.form_response.answers[5].text}}

Logged to CRM (Google Sheets).
