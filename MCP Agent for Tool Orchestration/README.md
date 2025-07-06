# 🧠 Jarvis: Telegram-Based AI Automation Agent using n8n & MCP

Jarvis is an intelligent AI assistant built on top of [n8n](https://n8n.io), integrated with the **MCP Client Tool**, and designed to receive commands through **Telegram** and execute tasks using various connected tools like Gmail, Google Sheets, and Google Drive.

This project demonstrates a fully functional natural language automation agent with tool orchestration using OpenAI or Claude.

---

## 🚀 Features

- 🤖 Accepts **natural language commands** via Telegram  
- 🧠 Uses **OpenAI/Claude** via MCP to interpret and route prompts  
- ⚙️ Supports multiple tools like:
  - Send email (SMTP)
  - Update or append rows in Google Sheets
  - Upload files to Google Drive
  - Respond via Telegram  
- 🔀 Supports **multi-tool chaining** in a single message  
- 🔒 Works with service account credentials (no token expiry issues)

---

## 🛠 Tools Registered in MCP Server

| Tool Name         | Description                                 |
|------------------|---------------------------------------------|
| `send_email`      | Sends email using SMTP (Gmail App Password) |
| `update_sheet`    | Appends logs or actions to Google Sheets    |
| `update_sheet_row`| Updates specific rows in Google Sheets      |
| `upload_file`     | Uploads files to a Google Drive folder      |
| `send_reply`      | Sends reply messages back to Telegram users |

---

## 📦 Architecture Overview

```
Telegram ➝ Function Node ➝ MCP Client ➝ MCP Server ➝ Selected Tools ➝ Telegram Response
```

- **Telegram Trigger**: Captures user message
- **Function Node**: Extracts `input` and `chatId`
- **MCP Client Node**: Sends the prompt to MCP Server
- **MCP Server Trigger Node**: Parses prompt using LLM and calls one or more tools
- **Tool Nodes**: SMTP, Google Sheets, Drive, etc.
- **Telegram Send Message**: Responds to user via `chatId`

---

## 🧾 Setup Instructions

1. Create a Telegram bot using BotFather and connect it as a trigger.
2. Create a Gmail App Password and configure the SMTP node.
3. Set up Google Service Account and share your Google Sheet and Drive folder with the service email.
4. Add and configure each tool (Email, Sheets, Drive) in n8n.
5. Use the **MCP Client** to send prompts and **MCP Server Trigger** to manage tools.
6. Add the system message in MCP Server Trigger's instruction field.

---
