# 💬 WhatsApp RAG Chatbot (n8n + Supabase + Postgres)

An AI-powered chatbot that runs on WhatsApp using only official n8n nodes — no custom HTTP calls. It answers user questions by retrieving relevant document chunks from Supabase and generating accurate replies using GPT (OpenAI or Claude). All interactions are saved in Postgres for long-term memory.

---

## 🔧 Tech Stack

- **WhatsApp** (Trigger & Reply)
- **Supabase** (Vector search via Select node)
- **OpenAI / Claude** (Answer generation)
- **Postgres** (Memory logging)
- **Google Drive** (File ingestion & chunking)

---

## 🧠 Workflow

1. **WhatsApp Trigger** receives user question  
2. **Supabase Select Node** retrieves top vector matches  
3. **OpenAI Node** summarizes context into a final answer  
4. **WhatsApp Reply Node** sends the response back  
5. **Postgres Insert** saves question + answer for memory  
6. *(Optional)* **Google Drive Ingestion** adds new files to Supabase

---

## 🗃️ Postgres Table

```sql
CREATE TABLE conversation_log (
  id SERIAL PRIMARY KEY,
  phone TEXT,
  question TEXT,
  answer TEXT,
  timestamp TIMESTAMPTZ DEFAULT NOW()
);


