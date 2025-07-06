# 🤖 Smart HR Agent with MCP & Telegram Interface

This workflow creates a smart HR assistant that interacts via **Telegram**, processes **natural language commands** using **OpenAI**, and updates/stores employee data in **Google Sheets**. It supports **multiple HR commands** using a logic system known as **MCP (Multi-Command Processing)**.

---

## 📌 Features

- 🧠 Understands plain-text commands like:
  - “Apply for leave from July 10 to 14”
  - “How many leaves do I have left?”
  - “Update my phone number to 0333-1234567”
- 📊 Stores and fetches data from Google Sheets
- 🧭 Uses MCP logic to route commands
- 💬 Responds to employees on Telegram
- ✅ Fully automated — no HR staff involvement needed

---

## 🛠️ Tech Stack (n8n Nodes)

| Function             | Node Type            |
|----------------------|----------------------|
| User input           | Telegram Trigger     |
| Intent detection     | OpenAI / Claude Node |
| Action routing       | Switch / IF Node     |
| Leave application    | Google Sheets (Append) |
| Balance check        | Google Sheets (Lookup) |
| Info update          | Google Sheets (Update) |
| User reply           | Telegram Node        |

---

## 🔁 Supported Actions via Natural Language

| Action          | Trigger Phrase Example                      | Sheet Interaction         |
|------------------|----------------------------------------------|----------------------------|
| `apply_leave`   | "I want leave from July 10 to July 14"       | Append row to Leave Sheet |
| `check_balance` | "How many leaves do I have left?"            | Lookup leaves left        |
| `update_info`   | "Update my phone to 0333-1111111"            | Update user record        |

---

## 🧩 How MCP Works (Multi-Command Processing)

1. Telegram receives user's message
2. Message is passed to OpenAI
3. OpenAI returns structured JSON like:
   ```json
   {
     "action": "apply_leave",
     "start_date": "2024-07-10",
     "end_date": "2024-07-14",
     "employee_name": "Fahad Warraich",
     "employee_contact": "0333-1234567"
   }
