# 🤖 Product Recommender Chatbot (AI Agent + Telegram + Google Sheets)

A smart AI shopping assistant built using **n8n**, **OpenAI**, **Telegram**, and **Google Sheets**. The bot understands natural language queries like  
_"Looking for a phone under $300 with a good camera"_  
and responds with the best product recommendations from a curated product list.

---

## 🧠 How It Works

### 🔄 Workflow Flow:
1. 🧾 **AI Agent BOT (Trigger)**  
   - User sends a message like: _"Suggest me a laptop under $800 for editing"_
   - AI Agent is connected to **OpenAI** and **Google Sheets** in the backend

2. 🧠 **GPT interprets the query**  
   - Extracts:  
     - Product category  
     - Budget  
     - Desired features (e.g. camera, battery, screen size)

3. 📊 **Google Sheets Lookup**  
   - Matches interpreted info with a product list in Google Sheets  
   - Filters products based on budget, category, and feature match

4. 📩 **Telegram Message**  
   - Bot sends back a neatly formatted message with product suggestions  
   - Each result includes name, price, key features, and buy link

---

## 🔧 Tech Stack

| Tool          | Purpose                          |
|---------------|----------------------------------|
| n8n           | Workflow automation              |
| AI Agent Bot  | Natural language trigger (MCP)   |
| OpenAI (GPT)  | Query understanding & reasoning  |
| Google Sheets | Product database                 |
| Telegram      | Message input/output interface   |

---

## 🗂️ Data Format (Google Sheets)

| name          | category | price | features                         | url                    |
|---------------|----------|-------|----------------------------------|------------------------|
| Redmi Note 12 | phone    | 250   | great camera, long battery       | https://buy.example.com |
| Dell XPS 13   | laptop   | 750   | editing, light weight, 16GB RAM  | https://buy.example.com |

---

## 💬 Sample Query

```text
"Looking for a phone under $300 with long battery life and great camera"
