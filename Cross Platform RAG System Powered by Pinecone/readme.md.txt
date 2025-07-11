🧠 Cross-Platform RAG System Powered by Pinecone
A Retrieval-Augmented Generation (RAG) system designed to handle user queries from multiple channels (WhatsApp, Slack, Telegram) and provide accurate, context-aware responses using OpenAI + Pinecone-powered knowledge base.

🚀 Features
🧵 Multi-Channel Query Handling
Accepts questions from:

WhatsApp

Slack

Telegram

Uses a shared channel handler to normalize messages

🔍 Retrieval-Augmented Generation (RAG)
AI Agent queries Pinecone Vector Store for relevant context

Performs semantic search via OpenAI Embeddings

Responds with highly relevant and accurate information

📚 Knowledge Base Creation
Uploads knowledge via PDF form submission

Extracts text and splits into chunks (Recursive Character Text Splitter)

Embeds and stores data in Pinecone

🔄 Context Routing
Dynamically switches response format based on trigger source

Sends results back through WhatsApp, Slack, or Telegram

⚙️ Architecture Overview
plaintext
Copy
Edit
📥 Incoming Query (WhatsApp/Slack/Telegram)
        ↓
🧭 Channel Normalizer
        ↓
🧠 AI Agent
   ↳ 🔎 Vector Retrieval via Pinecone
   ↳ 🧾 Embedding via OpenAI
        ↓
🗣 Formulate Answer
        ↓
📤 Return to User on Original Platform
🧩 Components
Module	Description
WhatsApp/Slack/Telegram Triggers	Event-based listeners for incoming messages
Channel Normalizer	Standardizes message handling
AI Agent	Main logic, reasoning, and response generation
Pinecone Vector Store	Stores embedded knowledge chunks
OpenAI Embeddings	Converts text to vectors for semantic search
Knowledge Base Builder	Form submission → PDF extraction → vector store
Response Dispatcher	Sends responses back to correct channel

🗂 Knowledge Base Workflow
User Submits a Form (with PDF)

Text Extracted from PDF

Chunking with Recursive Text Splitter

Embedding with OpenAI API

Storage in Pinecone Vector DB

🧪 AI Agent Behavior
Embedding comparison for document retrieval

Hybrid search using Pinecone + AI completion

Option to use multiple OpenAI models (e.g., GPT-3.5, GPT-4)

Supports query context switching between Vector Store Tools

📦 Technologies Used
🧠 OpenAI Chat Models

📊 Pinecone Vector Store

🧮 OpenAI Embedding API

💬 WhatsApp Business API

🛠 Slack & Telegram Bot APIs

📄 PDF Text Extractor

🔁 Recursive Character Text Splitter

🛠 Use Cases
Enterprise FAQ bots across platforms

Internal documentation query systems

Context-aware customer support agents

RAG-powered Slackbots or WhatsApp assistants

📬 Get Started
Configure Channel APIs (WhatsApp, Slack, Telegram)

Set up Pinecone account and vector store

Add OpenAI API keys

Deploy the form handler to build your KB

Start your agent and begin chatting!