# 📇 CRM Auto-Updater with HubSpot (n8n Workflow)

This workflow automatically captures new contact data submitted through a Typeform form, creates or updates the contact in HubSpot CRM, and sends a personalized welcome email.

---

## 🔁 Workflow Overview

### 🎯 Trigger:
- A **Typeform** form submission by a new user.

### 📥 Data Collected:
- Full Name
- Email Address
- Phone Number

---

## 🧩 Workflow Steps

1. **Typeform Trigger**
   - Activates when a user submits a form.

2. **Set / Function Node**
   - Extracts and formats data from the Typeform response:
     - `firstname`
     - `email`
     - `phone`

3. **HubSpot Node (Create or Update Contact)**
   - Uses n8n's native HubSpot integration.
   - **Resource**: `Contact`
   - **Operation**: `Create or Update`
   - Maps the following fields:
     - `email`: `{{ $json.email }}`
     - `firstname`: `{{ $json.firstname }}`
     - `phone`: `{{ $json.phone }}`
   - Ensures no duplicate contacts based on email.

4. **Email Node**
   - Sends a welcome message to the contact:
     - Subject: `"Welcome to Our Platform!"`
     - Message:
       ```
       Hi {{ $json.firstname }},

       Thanks for signing up. We're excited to have you with us.

       Best,
       The Team
       ```

---

## 🔧 Tools Used

| Tool        | Purpose                           |
|-------------|-----------------------------------|
| Typeform    | Form to collect contact info      |
| n8n         | Automation workflow               |
| HubSpot     | CRM platform for contact storage  |
| Email (SMTP/Gmail) | Sends the welcome email        |

---

## 🔐 Authentication

- ✅ **HubSpot OAuth Credential**: Set up using the HubSpot node
- ✅ **Email Credential**: Use Gmail or SMTP credentials in n8n

---

## ⚠️ Common Issues & Fixes

| Issue                        | Fix                                                 |
|-----------------------------|------------------------------------------------------|
| Phone number not saving     | Add `"phone"` manually in **Additional Fields** of HubSpot node |
| Email sends but name is missing | Ensure correct variable reference like `{{ $json.firstname }}` |
| Duplicate contacts           | HubSpot’s "Create or Update" handles duplicates via email |

---

## 🧪 Sample Typeform Mapping (via `answers` array)

| Question         | Field Ref   | Mapping Example                  |
|------------------|-------------|----------------------------------|
| Full Name        | name        | `{{ $json.answers[0].text }}`    |
| Email Address    | email       | `{{ $json.answers[1].email }}`   |
| Phone Number     | phone       | `{{ $json.answers[2].text }}`    |

---

## 💡 Suggestions for Extension

- 🔔 Add Slack/Telegram alerts for new contacts
- 📊 Log contact info in Airtable or Google Sheets
- 📬 Add a second follow-up email with a PDF or onboarding content

---

## 📎 License

This automation workflow is free to use, modify, and integrate. Attribution is welcome but not required.

---
