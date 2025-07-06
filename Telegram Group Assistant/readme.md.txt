# 🤖 Telegram Group Assistant (Hybrid AI + Google Sheets)

A smart n8n-powered Telegram bot that listens for `@mentions` in group chats and automatically replies with either:

✅ Answers from a connected Google Sheet  
🤖 Or an AI-generated response (using OpenAI or Claude) if no sheet match is found

---

## 📌 Features

- Listens for `@YourBotUsername` mentions in group messages  
- Extracts the user’s query  
- Searches for matching answers in Google Sheets  
- Uses AI (OpenAI or Claude) if no match is found  
- Replies inline in the group tagging the user  
- Fully no-code, runs inside [n8n](https://n8n.io)

---

## 🛠️ Prerequisites

1. **Telegram Bot** (create via [@BotFather](https://t.me/botfather))  
2. **Google Sheet** with 2 columns:
   ```
   | Question           | Answer                        |
   |--------------------|-------------------------------|
   | how to register?   | Visit www.site.com/register   |
   ```
3. **OpenAI or Claude API Key** (for fallback answers)  
4. Bot must be:
   - ✅ Added to your Telegram group  
   - ✅ Promoted to Admin  
   - ✅ Given permission to **read messages**

---

## 🔧 n8n Workflow Overview

| Step | Node                        | Description |
|------|-----------------------------|-------------|
| 1    | Telegram Trigger             | Detects `@mention` messages in group |
| 2    | Function Node (Extract Msg) | Removes @botname and parses query |
| 3    | Google Sheets - Lookup      | Searches question in Google Sheet |
| 4    | IF Node                     | Checks if answer is found |
| 5    | OpenAI Node (Optional)      | Fallback to AI if no answer found |
| 6    | Telegram - Send Message     | Replies in group tagging the user |

---

## 🧠 AI Agent – System Prompt (Use in AI Node)

```
You are a smart and friendly assistant inside a Telegram group.
Your job is to help members by answering their questions clearly, briefly, and respectfully.
Always be polite and helpful, and assume the user is looking for information related to the group.
If you are unsure of the exact answer, try your best to provide helpful context or a useful direction.

Do not mention that you are an AI or language model.
Respond as if you're a helpful human group admin who knows everything about the community.
```

---

## 📩 Example Message Flow

**User sends:**  
`@MyBot how do I reset my password?`

**Bot replies:**  
`@username 👉 You can reset your password by clicking “Forgot Password” on the login screen.`

---

## ✅ Tips for Success

- Make sure your Google Sheet is shared with your n8n service account
- Make your AI responses concise and relevant to your group
- Use logging for missed questions to improve your Sheets/FAQ over time

