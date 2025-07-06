# 📅 AI-Powered Meeting Planner with n8n, MCP, and Telegram

This project implements a fully automated, AI-powered meeting scheduler using [n8n](https://n8n.io), [MCP (Multi-Tool Command Processor)](https://docs.n8n.io/integrations/tools/mcp/), and **Telegram**. It enables users to create calendar events with natural language commands like:

> “Set a call with Alex next Thursday at 3”

The system extracts key details (title, date, time, participant) using an AI model via the MCP Client and then creates a Google Calendar event, sends a confirmation email, and replies on Telegram — all automatically.

---

## 🚀 Features

- 📲 Accepts natural language instructions via Telegram
- 🧠 Parses time, date, and participant using OpenAI or Claude via MCP
- 📆 Creates a Google Calendar event with exact timing
- 📧 Sends confirmation email automatically
- 💬 Sends reply back to Telegram user
- 🔄 Multiple tool orchestration in one flow

---

## 🧰 Tools Registered in MCP Server

| Tool Name             | Description                                 |
|-----------------------|---------------------------------------------|
| `create_calendar_event` | Creates a new event in Google Calendar     |
| `send_email`            | Sends email via SMTP or Gmail              |
| `send_reply`            | Sends confirmation back to Telegram        |

---

## 📦 Architecture

```
Telegram ➝ Function Node ➝ MCP Client ➝ MCP Server ➝ [Calendar + Email + Telegram] Tools
```

---

## 🔧 Setup Instructions

1. Create a Telegram bot and connect it as the trigger node.
2. Add a Function node to extract `input` and `chatId` from the Telegram message.
3. Pass those values into the MCP Client node.
4. On the MCP Server Trigger node, register three tools:
    - `create_calendar_event`
    - `send_email`
    - `send_reply`
5. Configure Google Calendar and Email nodes using your credentials.
6. Add the proper instruction in the system message to let the AI know what tools are available and how to use them.
7. Test the flow by sending a message like:  
   _“Schedule meeting with John on Friday at 10am”_

---

