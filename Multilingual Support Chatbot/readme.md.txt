# 🌍 Multilingual Support Chatbot (n8n Workflow)

A fully automated, AI-powered chatbot built with n8n that supports users in any language. It detects the incoming message's language, translates it to English for processing with GPT (OpenAI or Claude), and then translates the response back into the original language before replying.

---

## 📌 Features

- Detects language of incoming user message
- Translates message to English (for GPT processing)
- Generates intelligent replies using OpenAI/Claude
- Translates response back to original language
- Sends reply inline to the user on their messaging platform

---

## 🛠️ Prerequisites

1. **n8n Account** (Self-hosted or Cloud)
2. **OpenAI API Key** (or Claude, optional)
3. **Translation API**:
   - Google Cloud Translate OR
   - DeepL API
4. **Messaging Platform Bot** (Telegram, WhatsApp, etc.)
5. Bot must be:
   - ✅ Added to your group/channel/user chat
   - ✅ Have permission to read and send messages

---

## 🔁 Workflow Overview

| Step | Node                          | Description |
|------|-------------------------------|-------------|
| 1    | **Trigger Node**              | Telegram Trigger / Webhook |
| 2    | **Language Detection Node**   | Detects source language |
| 3    | **Translate to English**      | Translate to English (via Google/DeepL) |
| 4    | **OpenAI Node**               | Generates smart reply in English |
| 5    | **Translate Back to Original**| Converts GPT reply back to source language |
| 6    | **Send Message Node**         | Sends response to user inline |

---

## 🧠 AI Agent – System Prompt

Use this system message inside your OpenAI/Claude node:

```
You are a professional multilingual support agent. 
You always answer clearly, respectfully, and helpfully in English. 
Make sure your answers are concise and suitable for translation.
```

---

## 📩 Example Flow

**Incoming Message (Spanish):**
```
Hola, ¿cómo puedo actualizar mi dirección?
```

**Bot Workflow:**
- Language detected: Spanish
- Translated to English: "Hello, how can I update my address?"
- GPT reply: "You can update your address in your account settings."
- Translated back to Spanish: "Puede actualizar su dirección en la configuración de su cuenta."
- Sent to user ✅

---

## ✅ Notes & Tips

- Use `Google Translate API` for wide language coverage
- Use `DeepL` for better translation quality (especially European languages)
- Log all original queries and responses for quality checks
- Handle long messages with summarization if needed

