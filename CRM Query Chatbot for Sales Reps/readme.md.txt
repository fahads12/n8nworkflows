# 🤖 CRM Query Chatbot for Sales Reps (n8n Workflow)

An AI-powered chatbot built using **n8n**, allowing sales reps to query CRM data (from Google Sheets) using natural language via Telegram. The bot uses OpenAI to interpret the question, fetches relevant data, and returns the results directly in chat.

---

## 🧠 How It Works

### 🔄 Flow Summary

1. **💬 Telegram Trigger**  
   Captures incoming queries like:  
   - _"Show hot leads from today"_  
   - _"How many leads came in last week?"_

2. **🧠 AI Chatbot (OpenAI)**  
   Parses the query and converts it into a structured JSON format (e.g., date range, lead status)

3. **📦 Structured Output Parser**  
   Extracts usable JSON from the AI output (e.g., `"date_range": "last 7 days"`)

4. **📊 Google Sheets Query**  
   Reads all leads from the CRM sheet  
   Filters leads based on the AI's extracted logic

5. **📨 Telegram Send Node**  
   Sends the final list or summary back to the sales rep in Telegram

---

## 🛠 Tools Used

| Tool/Service           | Purpose                            |
|------------------------|------------------------------------|
| Telegram Bot           | Interface for sales reps           |
| n8n                    | Workflow automation engine         |
| OpenAI (via AI Agent)  | Natural language query processing  |
| Structured Output Parser | Converts AI output to JSON        |
| Google Sheets          | CRM / Lead data source             |
| Telegram (Send Node)   | Responds with data in chat         |

---

## 🧾 Example Query

**User Message (via Telegram):**
