# 🧠 Knowledge Base RAG Chatbot (n8n + Supabase + Telegram + Postgres)

This project is an AI-powered RAG (Retrieval-Augmented Generation) chatbot built on top of [n8n](https://n8n.io), using Supabase as a vector store, Postgres for long-term memory, and Telegram for real-time interaction. It enables users to ask any internal support question and receive a concise AI-generated answer based on indexed documents.

---

## 🚀 Features

- 📥 Accepts questions via Telegram
- 🔍 Searches embedded documents in Supabase Vector Store
- 🧠 Uses OpenAI/Claude to generate context-aware answers
- 💬 Replies back to users via Telegram
- 🗃 Logs all interactions into Postgres
- 📂 Optionally supports file ingestion via Google Drive

---

## 🧰 Tools Used

| Tool / Service     | Purpose                                        |
|--------------------|------------------------------------------------|
| Telegram Bot       | Accepts user queries and sends replies         |
| Supabase           | Stores vector embeddings of documents          |
| OpenAI / Claude    | Summarizes relevant content for final response |
| Postgres           | Saves conversation history                     |
| Google Drive       | Ingests and indexes new documents              |
| n8n Nodes          | Orchestrates the workflow                      |

---

## 🔧 Architecture Overview


---

## ⚙️ Setup Instructions

### 1. Telegram Bot
- Create a bot via BotFather
- Connect it using the Telegram Trigger node

### 2. Supabase Vector Search
- Set up Supabase with pgvector and embedding endpoint
- Create a search function or use REST API for top-K vector match

### 3. OpenAI / Claude
- Connect your OpenAI or Anthropic API key
- Use a prompt template to summarize based on retrieved content

### 4. Postgres Memory
- Set up a table `conversation_log` with fields: `chat_id`, `question`, `answer`, `timestamp`
- Insert user prompts and responses automatically

### 5. Google Drive Ingestion (Optional)
- Use Google Drive Trigger or Poll node
- Download PDF files
- Chunk and embed via Supabase API

---

## 🧪 Example Prompt

> “How do I request a travel reimbursement?”

Chatbot response (via Telegram):
> ✅ To request a travel reimbursement, fill out the expense form linked in policy.pdf (Section 3). Submit it to finance@company.com before the 5th of the month.

---

## 🙌 Optional Enhancements

- Add Notion for internal admin log
- Use Google Sheets for indexed document records
- Add file upload via Telegram → auto-embed into Supabase
- Add multilingual support via GPT system prompt

