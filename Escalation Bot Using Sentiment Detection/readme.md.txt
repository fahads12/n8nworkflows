# 🚨 Escalation Bot Using Sentiment Detection

This n8n workflow automatically detects angry or negative customer messages and escalates them to a human agent while logging the issue into Google Sheets for tracking. Powered by OpenAI for sentiment analysis and structured parsing, it’s ideal for customer retention and real-time issue handling.

---

## 🧠 How It Works

### 🔁 Flow Overview

1. **🟢 Telegram Trigger**  
   The workflow starts when a user sends a message to your Telegram bot.

2. **🤖 AI Agent (OpenAI)**  
   The message is passed to OpenAI to analyze and classify sentiment, and extract:
   - Name (if included)
   - Original message
   - Sentiment (`positive`, `neutral`, or `negative`)

3. **📦 Structured Output Parser**  
   Ensures the AI response is returned in a clean JSON format with consistent keys.

4. **🕵️‍♂️ Escalation Logic**  
   If sentiment is **negative**, the bot:
   - Sends an escalation alert to your admin (optional)
   - Logs the issue in Google Sheets

5. **📝 Google Sheets Output**  
   The following fields are written to Google Sheets:
   - `Name`
   - `Message`
   - `Sentiment`
   - `Timestamp`

---

## 🧩 Tech Stack

| Component              | Role                                |
|------------------------|-------------------------------------|
| Telegram Bot           | Customer interface (message input) |
| n8n                    | Workflow orchestration              |
| OpenAI (via AI Agent)  | Message analysis and sentiment detection |
| Structured Output Parser | Converts AI text into JSON fields |
| Google Sheets          | Logging and issue tracking          |

---

