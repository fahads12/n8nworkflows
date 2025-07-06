# 📁 File Uploader Bot with Analysis (n8n Workflow)

An AI-powered Telegram bot that allows users to upload PDF files. It extracts and summarizes key information like invoice number, date, and total amount using a combination of PDF parsing and AI analysis. Built with n8n for seamless automation.

---

## ⚙️ Workflow Overview

**Trigger:**  
📤 User sends a PDF file via Telegram

**Flow:**
1. Receive file from Telegram
2. Download and parse PDF to extract raw text
3. Analyze extracted text with AI (OpenAI or Claude)
4. Extract key fields (Invoice Number, Date, Amount, Vendor)
5. Send summary back to user via Telegram

---

## 🔧 Tech Stack

| Tool | Purpose |
|------|---------|
| [n8n](https://n8n.io/) | Workflow automation engine |
| Telegram Bot | Frontend interface (file input & output) |
| PDF Parser (`pdf-parse` or PDF.co) | Extracts text from uploaded PDF |
| OpenAI / Claude | AI model to interpret document and extract fields |
| Google Sheets / Notion *(optional)* | Store summary results |

---

## 📦 Setup Instructions

1. **Clone or Import the Workflow**
   - Use the provided `.json` file to import into n8n

2. **Create and Connect Your Telegram Bot**
   - Create a bot using [BotFather](https://t.me/botfather)
   - Copy the token and configure the Telegram Trigger and Send Message nodes

3. **Set Up PDF Parsing**
   - Option A: Use `pdf-parse` in a Function node (self-hosted n8n)
   - Option B: Use PDF.co API (requires API key)

4. **Configure AI Integration**
   - Use OpenAI or Claude node (or HTTP node) with appropriate prompts:
     ```text
     Extract Invoice Number, Vendor Name, Date, and Total Amount from the following text:
     {{ $json.text }}
     ```

5. **Test the Bot**
   - Send a PDF file in Telegram to see the extracted summary returned.

---

## ✅ Example Output

```text
📄 Invoice Summary  
Invoice #: INV-00924  
Vendor: ABC Supplies Ltd.  
Date: 2024-10-12  
Amount: $3,150.00
