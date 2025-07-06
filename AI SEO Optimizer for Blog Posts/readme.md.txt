# 🧠 AI SEO Optimizer for Blog Posts (n8n + MCP + Telegram/WhatsApp)

This project is a smart, AI-powered SEO analysis assistant that accepts blog content through Telegram or a Google Form and returns actionable SEO feedback using OpenAI, all orchestrated through the MCP tool in [n8n](https://n8n.io).

It checks for title tag, keyword density, readability, and structural issues, and replies with personalized recommendations via Telegram or WhatsApp.

---

## 🚀 Features

- 📥 Accepts blog text from Telegram or Google Form
- 🔍 Uses OpenAI to:
  - Check title tag presence
  - Measure keyword density
  - Assess readability (Flesch score)
  - Review paragraph structure
- 📤 Returns suggestions via Telegram or WhatsApp
- 🛠 Powered by n8n + MCP for modular, scalable AI automation

---

## 🧰 MCP Tools Registered

| Tool Name       | Description                                     |
|------------------|-------------------------------------------------|
| `analyze_seo`    | Analyzes the blog for SEO metrics using OpenAI |
| `send_reply`     | Sends the summary back via Telegram/WhatsApp   |

---

## 📦 Architecture Overview


---

## 🔧 Setup Instructions

1. **Trigger Setup**
   - Use either:
     - Telegram Bot (Telegram Trigger Node)
     - Google Form → Webhook → Webhook Trigger Node

2. **Function Node**
   - Extract:
     - `input`: full blog text
     - `chatId`: from Telegram (optional for Forms)

3. **MCP Client Node**
   - Pass the `input` and `chatId` as JSON payload to MCP Server.

4. **MCP Server Trigger**
   - Register the following tools:
     - `analyze_seo` → uses OpenAI to extract feedback
     - `send_reply` → replies with summarized SEO suggestions

5. **OpenAI Configuration (inside analyze_seo)**
   - Use a prompt that instructs the model to check title tags, density, readability, and provide clear bullet-point feedback.
   - Keep responses plain and structured.

6. **Respond via Telegram or WhatsApp**
   - Use `send_reply` tool and return results to user using `chatId` or phone number (if WhatsApp).

---




