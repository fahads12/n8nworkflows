# 🧠 Travel Booking Agent with Long-Term Memory (n8n Workflow)

This workflow builds a smart AI agent connected to **Telegram** that helps users plan trips and remembers past conversations using **PostgreSQL** for long-term memory.

---

## 🗺️ Overview

### 🔁 Workflow Summary

| Component       | Purpose                                              |
|------------------|------------------------------------------------------|
| **Telegram**     | Interface to chat with users                         |
| **OpenAI GPT**   | Powers the AI assistant for travel planning          |
| **PostgreSQL**   | Stores and retrieves user conversation history       |
| **n8n**          | Orchestrates the logic and connections               |

---

## 🧩 How It Works

1. **User sends a message** via Telegram
2. **n8n captures the message** using Telegram Trigger node
3. System:
   - Extracts `user_id`, `username`, `message`
   - Loads past messages for that user from PostgreSQL (if available)
   - Compiles conversation history + current message
4. Sends combined prompt to **OpenAI GPT**
5. AI replies with personalized travel help
6. Reply is sent back via Telegram
7. This chat round (user + AI) is saved into **PostgreSQL memory**

---

## 💾 PostgreSQL Memory Schema

You must have a table like this:

```sql
CREATE TABLE conversation_memory (
  id SERIAL PRIMARY KEY,
  user_id TEXT,
  username TEXT,
  user_message TEXT,
  ai_response TEXT,
  timestamp TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
