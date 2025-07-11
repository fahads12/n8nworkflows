🤖 WhatsApp Chatbot for Customer Service & Low-Ticket Sales
This project implements a powerful and intelligent WhatsApp chatbot using n8n, AI models, and vector search to automate customer support and low-ticket product sales. It supports text and voice inputs, retrieves company knowledge using RAG (Retrieval-Augmented Generation), and responds conversationally.

🧩 Key Features
🟢 WhatsApp input for both audio and text

🎙 Automatic speech-to-text for audio messages

🧠 RAG-based AI Agent with persistent memory

📁 Upload and embed company documents in a vector database

💬 Smart replies to user queries using contextual memory

💼 Useful for customer service, FAQs, and product recommendations

📚 Workflow Breakdown
1. Redirect Message Based on File Type
(Green Block - Input Handler)

WhatsApp Trigger: Receives incoming messages.

Split Message Parts: Parses incoming message content.

Redirect Message Types: Routes audio and text to appropriate processors.

2. Converting Audio to Text
(Brown Block - Audio Pipeline)

Get Audio URL → Download Audio

Uses Google Gemini to transcribe audio.

Result is sent to the shared message processing pipeline.

3. Store Your Company’s Documents in Vector Database
(Brown Block - Vector Store Setup)

Upload your company documents manually.

Documents are processed by:

Text Splitter

Data Loader

OpenAI Embeddings

Stored in Supabase Vector Store for efficient retrieval during chat.

4. Company Knowledge RAG Agent with Persistent Memory
(Blue Block - AI Engine)

AI Sales Agent (chat node):

Uses OpenAI Chat Model with Vector Memory.

Fetches context from stored documents via vector search.

Vector Store Tool & Supabase Store for RAG

Replies to users on WhatsApp using context-aware and accurate responses.

🖼 Architecture Diagram

🔧 Prerequisites
n8n instance (self-hosted or cloud)

WhatsApp Business API or Twilio WhatsApp integration

Google Gemini API (for transcription)

OpenAI API key

Supabase account & vector store plugin (e.g., pgvector)

Optional: Document loader & splitter packages

⚙️ Setup Guide
Connect your WhatsApp API to the trigger node.

Configure Google Gemini API credentials.

Set up Supabase vector DB and create necessary tables.

Provide OpenAI credentials in the vector embedding and RAG nodes.

Upload documents to be indexed.

Test by sending a message or voice query via WhatsApp!

✅ Use Cases
📞 Customer Support: Handle common queries 24/7

🛍️ Product Guidance: Recommend products using your company data

🧾 FAQ Handling: Automate responses for repeat questions

🎙 Voice Interaction: Let users speak instead of typing

💡 Highlights
Handles both voice and text inputs

Uses RAG with OpenAI + Supabase for smart, company-specific answers

Scalable for small businesses or enterprises

