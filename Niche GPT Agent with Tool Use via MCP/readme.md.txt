# 🤖 Niche GPT Agent with Tool Use via MCP (n8n Workflow)

This project implements a smart **AI Agent** inside [n8n](https://n8n.io) using **Multi-Command Processing (MCP)**. It intelligently interprets natural language prompts and performs one of three dynamic actions:

- 🔍 Search a Notion database  
- 📧 Send an email  
- 🌐 Call a public API  

The agent uses OpenAI or Claude to understand the intent behind the prompt and selects the appropriate tool — fully automated, no manual routing required.

---

## 🚀 Features

- ✅ Accepts natural language prompts via webhook (e.g. from Postman or frontend)
- 🧠 Uses Claude or OpenAI to interpret the command via MCP
- 🔁 Automatically routes to:
  - Notion database search
  - Email sender (SMTP/Gmail)
  - HTTP API call (e.g., cat fact API)
- 📩 Returns a structured response back to the webhook (Postman or frontend)
- ⚙️ Built entirely in **n8n** (no-code/low-code platform)

---

## 🧰 Tools & Nodes Used

| Purpose         | Node Type        |
|----------------|------------------|
| Input Trigger   | Webhook          |
| AI Reasoning    | Claude/OpenAI (MCP) |
| Output Parser   | Function         |
| Tool Routing    | Switch           |
| Tool: Notion    | Notion → Search |
| Tool: Email     | Gmail / SMTP     |
| Tool: API       | HTTP Request     |
| Output Response | Respond to Webhook |
| Formatter       | Set (optional)   |

---

## 🧪 How It Works (Flow Overview)

1. **Trigger:** Webhook receives a user prompt like “Tell me a cat fact” or “Search for project notes”.
2. **MCP AI Agent:** OpenAI/Claude returns structured JSON with tool and task.
3. **Function Node:** Parses and flattens JSON from AI.
4. **Switch Node:** Chooses which tool to use (`notion`, `email`, `api`).
5. **Tool Execution:** Executes the chosen tool.
6. **Webhook Respond Node:** Sends back a clear result to the sender.

---

## 📬 Example Prompt & Response

### 🧠 Prompt (Webhook Input)
```json
{
  "user_prompt": "Tell me a random cat fact"
}
