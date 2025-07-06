# 🤖 Booking Chatbot with Confirmation (n8n Workflow)

This is an AI-powered appointment booking chatbot built using **n8n**, **Telegram**, **OpenAI**, and **Google Sheets**. Users can book services by sending natural messages like:

> “Book a haircut tomorrow at 4pm”

The bot understands the request, checks if the time is available, stores it, and sends back a confirmation.

---

## 🧠 AI Agent System Prompt

```text
You are a professional booking assistant for a salon or service business. Your task is to extract structured booking information from the user's message and check the requested time slot's availability in the booking database (Google Sheets).

The user's message is:
{{ $json.message.text }}

Instructions:

1. Extract the following:
   - service (e.g., haircut, massage)
   - datetime (in ISO 8601 format: YYYY-MM-DDTHH:MM:SS)
   - name (use "Username" if not specified)
   - notes (optional)

2. Before confirming, check Google Sheets for an existing booking at the same datetime.

- If already booked, return:
```json
{
  "error": "The requested time slot is already booked. Please choose a different time."
}

If available, return:

json
Copy
Edit
{
  "service": "haircut",
  "datetime": "2025-07-06T16:00:00",
  "name": "Username",
  "notes": ""
}

Only return valid JSON. No extra explanation.

yaml
Copy
Edit

---

## 💬 Example User Message

I want to book a massage next Friday at 5 PM.

yaml
Copy
Edit

---

## 🤖 Example AI Output (JSON)

```json
{
  "service": "massage",
  "datetime": "2025-07-12T17:00:00",
  "name": "Username",
  "notes": ""
}

If slot is already booked:

json
Copy
Edit
{
  "error": "The requested time slot is already booked. Please choose a different time."
}
