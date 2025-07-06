# 🏥 Healthcare Appointment Reminder Workflow (n8n)

This is an **automated workflow for clinics or healthcare providers**, built using [n8n](https://n8n.io). It automatically sends appointment confirmations and reminders using:

- ✅ Google Sheets (Trigger)
- ✅ Gmail (Send confirmation email)
- ✅ Google Calendar (Add event)
- ✅ Telegram (Send chat reminder)

---

## 📌 Use Case

When a new patient is added to a Google Sheet, the system will:

1. 📥 **Trigger** when a new row is added in Google Sheets.
2. 📧 **Send a confirmation email** to the patient.
3. 📅 **Add the appointment to Google Calendar**.
4. 💬 **Send a Telegram reminder** to the patient using their Chat ID.

---

## 🔧 Requirements

- An [n8n instance](https://n8n.io)
- Connected Google services:
  - Google Sheets
  - Gmail
  - Google Calendar
- A [Telegram bot](https://t.me/BotFather)
- Telegram Chat IDs of the patients
- A Google Sheet with the following columns:

```text
| name | email | appointment_date | appointment_time | telegram_chat_id |
