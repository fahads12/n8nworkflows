# 🎓 College Info Bot - RAG Agent with Telegram & Supabase

This n8n workflow is an AI-powered chatbot designed to answer student queries related to degree programs, admissions, fees, and more. It uses Telegram as the user interface and leverages RAG (Retrieval-Augmented Generation) via Google Gemini or OpenAI, with vector search handled by Supabase.

---

## 📌 Features

- **Chat Interface**: Telegram Bot (bi-directional conversation)
- **Embeddings**: Google Gemini for generating embeddings
- **Vector Database**: Supabase Vector Store
- **Chat Memory**: PostgreSQL memory for context-aware conversations
- **Document Loader**: Google Drive integration to auto-process and embed new college documents

---

## 🔁 Workflow Breakdown

### 🤖 Telegram RAG Chatbot Flow

1. **Telegram Trigger**
   - Listens for new messages from users on Telegram.

2. **College Info Bot (LLM Agent)**
   - Uses `OpenAI Chat Model` or another LLM to generate responses.
   - Memory: `Postgres Chat Memory` to keep context.
   - Vector Search: `Supabase Vector Store` with `Google Gemini Embeddings`.

3. **Response via Telegram**
   - Sends the AI-generated answer back to the user using Telegram's `sendMessage`.

---

### 📂 Document Ingestion Flow (Google Drive → Vector Store)

1. **Google Drive Trigger**
   - Watches for newly uploaded documents.

2. **Download File**
   - Retrieves the document to be processed.

3. **Loop Over Items**
   - Iterates over each file or document part (e.g., pages, paragraphs).

4. **Embedding & Vector Storage**
   - Uses `Embeddings Google Gemini` to generate vector representations.
   - Stores embeddings into `Supabase Vector Store` via `Default Data Loader`.

---

## 🧠 Technologies Used

| Tool | Purpose |
|------|---------|
| Telegram | User-facing chatbot |
| n8n | Workflow automation |
| OpenAI / Gemini | LLM for answering questions |
| Supabase | Vector search |
| Google Drive | Source for uploading college info |
| PostgreSQL | Chat memory for multi-turn conversation |

---

## 🧰 Setup Instructions

1. **Set up Telegram Bot**
   - Create a Telegram bot using BotFather
   - Get your bot token and configure the Webhook URL in n8n

2. **Set up Supabase**
   - Create a project
   - Enable vector extension in PostgreSQL
   - Store embeddings with document metadata

3. **Configure LLMs**
   - Use OpenAI API Key or Gemini API Key in respective nodes

4. **Set up Google Drive Integration**
   - Use OAuth2 or Service Account credentials
   - Configure watch folder for document ingestion

5. **Deploy in n8n**
   - Import the workflow JSON
   - Add credentials to respective nodes
   - Enable the workflow

---

## 📄 Example Query

**User:** _"What degrees do you offer in Business?"_

**Bot:** _"We offer a BSc Business Administration from Royal Holloway, a Higher National Diploma from Pearson, and a BTEC Foundation Diploma. All programs are 3 years long with flexible entry routes."_

---

## 📎 Tags

`RAG` `n8n` `Telegram Bot` `Supabase` `Google Gemini` `OpenAI` `College Info Assistant` `AI Chatbot` `Embeddings` `Google Drive` `Document Processing`

---

## 📬 Contact

For support, please raise an issue or contact the project maintainer.
