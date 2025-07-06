# 📋 Job Application Tracker – n8n Workflow

This n8n automation tracks job applications submitted via a Typeform, stores them in Notion, and instantly notifies the recruiter on Slack.

---

## 🚀 Workflow Overview

1. **Typeform** – Collects job application data  
2. **Webhook (n8n)** – Receives the form submission  
3. **Notion** – Saves the applicant's details to a database  
4. **Slack** – Sends a message to notify the recruiter

---

## 🧩 Nodes Used

- 🔗 Webhook (to receive Typeform data)
- 📄 Notion (to store application)
- 💬 Slack (to send recruiter notification)

---

## 📥 Step 1: Typeform Setup

Create a form with fields such as:

- Full Name (short text)
- Email Address
- Role Applied For
- CV Upload (file upload or external link)
- Additional Notes (optional)

Then go to:

**Connect → Webhooks → Add Webhook**  
Set the webhook URL to:


Submit a test form to allow n8n to capture the structure.

---

## 🌐 Step 2: n8n Workflow

### 🔹 Webhook Node

- **Method**: `POST`
- **Path**: `job-application`

Captures the Typeform submission and passes it to Notion.

---

### 🔹 Notion Node – Create Record

Stores the application in your Notion database with the following fields:

| Notion Field     | Mapped From (Typeform Answer)               |
|------------------|---------------------------------------------|
| Name             | `{{$json.form_response.answers[0].text}}`   |
| Email            | `{{$json.form_response.answers[1].email}}`  |
| Role             | `{{$json.form_response.answers[2].text}}`   |
| CV Link          | `{{$json.form_response.answers[3].url}}`    |
| Status           | `Pending` *(default static value)*

> ℹ️ Adjust indices depending on your form structure.

---

### 🔹 Slack Node – Send Recruiter Notification

Sends a message to the recruitment channel like `#hiring` or `#recruitment`.

**Example Message:**
```markdown
📥 New Job Application Received

👤 Name: {{$json.form_response.answers[0].text}}  
📧 Email: {{$json.form_response.answers[1].email}}  
🎯 Role: {{$json.form_response.answers[2].text}}  
📎 CV: {{$json.form_response.answers[3].url}}

Please review and update status in Notion.
