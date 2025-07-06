# 🛍️ E-Commerce Order Notification Bot (n8n Workflow)

This n8n automation handles e-commerce order processing using a webhook triggered by **Postman** (or any custom front-end). It logs the order to **Notion**, sends a **confirmation email to the customer**, and posts a **notification to Slack**. It also conditionally alerts the team if the customer is a **VIP** or the order exceeds **$100**.

---

## 📦 Workflow Overview

### 🔄 Flow:

1. **Trigger** → Webhook (Order data from Postman)
2. **Format** → Use Set node to prepare item list and formatted price
3. **Save** → Log order in Notion
4. **Notify** → Send email to the customer
5. **Alert** → Post to Slack (standard)
6. **Condition** → IF VIP or high-value
7. **Special Alert** → Post to Slack (high-priority)

---

## 🚀 Sample Payload

Use this JSON in Postman to trigger the workflow:

```json
{
  "customer_name": "Alicia Thomas",
  "email": "alicia@example.com",
  "order_total": 149.99,
  "items": [
    { "name": "Phone Case", "qty": 1, "price": 19.99 },
    { "name": "Wireless Charger", "qty": 1, "price": 129.99 }
  ],
  "vip": true
}
