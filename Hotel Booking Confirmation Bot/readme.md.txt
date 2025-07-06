# 🏨 Hotel Booking Confirmation Bot (n8n Workflow)

This n8n workflow automates hotel booking confirmations. When a guest submits a booking form, the workflow stores the booking in Airtable, sends an email confirmation with a unique booking ID to the guest, and alerts the hotel staff on Slack.

---

## ✅ Use Case

Automate the hotel booking process:
- Accept bookings via a web form
- Store structured data in Airtable
- Instantly confirm bookings via email
- Alert your team in Slack

---

## ⚙️ Workflow Overview

- **Trigger**: Webhook (receives booking form submission)
- **Logic**: Generate a unique booking ID
- **Actions**:
  - Save booking in Airtable
  - Send confirmation email to guest
  - Send Slack message to hotel team

---

## 🧱 Workflow Steps

1. **Webhook Node**  
   - Listens for incoming POST requests from a form  
   - Expects JSON input:
     ```json
     {
       "name": "John Smith",
       "email": "john@example.com",
       "checkin_date": "2025-07-15",
       "checkout_date": "2025-07-18",
       "room_type": "Deluxe Suite"
     }
     ```

2. **Function Node**  
   - Generates a unique booking ID:
     ```
     HBK-xxxxx (e.g., HBK-94631)
     ```

3. **Airtable Node**  
   - Adds the booking to your Airtable table  
   - Required fields:
     - Name
     - Email
     - Check-in
     - Check-out
     - Room Type
     - Booking ID

4. **Email Node**  
   - Sends a confirmation email to the customer  
   - Includes booking details and contact message

5. **Slack Node**  
   - Sends a booking alert to your Slack channel  
   - Includes guest name, room, and check-in/check-out dates

---

## 📧 Email Sample

