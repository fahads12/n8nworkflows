🤖 MCP-Powered WhatsApp AI Agent
(with Voice, Image, and Tool Support)
This project is a powerful AI assistant built on Model Context Protocol (MCP), enabling rich multimodal and contextual conversations over WhatsApp. It supports text, voice, and image inputs, integrates with productivity tools, and routes data through intelligent agents enhanced with memory, knowledge, and plugins.

🧠 What is MCP?
Model Context Protocol (MCP) is a context-aware orchestration layer designed to:

Route and enrich messages intelligently

Enable persistent memory across sessions

Activate the right tools (ToDos, Emails, Social, etc.)

Support multi-modal input (Text, Voice, Image)

Interface with AI agents for reasoning and generation

🔧 System Overview

🧩 Core Components
Component	Functionality
WhatsApp Trigger	Captures incoming messages from WhatsApp
Switch Node	Routes message types (text, audio, image)
AI Agent	Core reasoning engine using OpenAI GPT with memory and tools
MCP Server Trigger	Allows internal tasks and workflows to trigger the AI agent
Voice Handler	Transcribes voice and generates audio replies
Image Handler	Analyzes and interprets incoming images
Tool Modules	Add support for Email, ToDos, Contacts, Social, etc.
Content Creator Agent	Specialized sub-agent for writing & creative generation

✨ Features
🎙️ Voice Support
Transcribe WhatsApp voice messages

Use TTS to reply back in voice

🖼️ Image Understanding
Analyze image content (OCR, objects, etc.)

Generate image-based prompts and replies

💬 Text Understanding
Handle WhatsApp messages contextually

Support question-answering, task automation, etc.

📚 Knowledge + Memory
Query long-term knowledge base (via OpenAI embeddings)

Retain session memory with Simple Memory module

🛠 Tool Integrations
ToDos: View, add, and update tasks

Email: Read, draft, and send emails

CRM: Fetch contacts from database

Social Media: Generate content posts

Custom Workflows: Trigger internal or external actions

🔗 Dependencies
OpenAI GPT (Chat, Embeddings)

Whisper / Speech-to-Text

TTS / Voice Generation API

WhatsApp Business Cloud API

MCP Protocol Engine (custom orchestration logic)

SerpAPI (optional for web search)

Database (for contact, memory, knowledge, etc.)

🚀 How It Works (Flow Summary)
Incoming Message via WhatsApp → Trigger

Switch → Route to Text / Voice / Image Handler

Handler processes content and forwards to AI Agent

AI Agent reasons using memory, tools, and context

Based on intent:

Respond with text or voice

Trigger tools (e.g., send email, create task)

Query knowledge base

Output is sent back via WhatsApp


🛡️ Use Cases
Customer Support Automation

Virtual Assistant for Teams

CRM and Sales Follow-ups via WhatsApp

Personal Productivity via Messaging

Content Generation & Social Posting