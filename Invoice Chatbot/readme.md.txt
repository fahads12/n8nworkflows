# 📄 Invoice Chatbot (n8n Workflow)

An AI-powered chatbot that generates and sends PDF invoices on demand via Telegram. Built using n8n, OpenAI, PDF.co, and Google Sheets, the bot extracts invoice IDs from user messages, fetches the relevant data, creates a custom invoice in PDF format, and sends it back through chat.

---

## 🧠 How It Works

### 🔁 Workflow Overview:

1. **🚀 Telegram Trigger**
   - Captures incoming message from user (e.g., "Send me invoice 123")

2. **🧠 Invoice Chatbot (MCP / AI Agent)**
   - Connected to OpenAI, Google Sheets, and a Structured Output Parser
   - Extracts:
     - `invoice_id` from user message
     - Retrieves matching row from Google Sheet
     - Formats structured JSON output

3. **🖋️ HTML Template Generator**
   - Uses the structured JSON data to generate a full HTML invoice template

4. **📄 PDF.co API**
   - Converts the HTML invoice to a downloadable PDF using PDF.co

5. **🌐 HTTP Request Node**
   - Downloads the PDF file from the PDF.co URL as binary data

6. **📩 Telegram Document Sender**
   - Sends the PDF back to the user via Telegram as a downloadable document

---

## 🧰 Tools & Services Used

| Tool               | Role                                 |
|--------------------|--------------------------------------|
| Telegram Bot        | Message interface with the user     |
| n8n                 | Automation & orchestration engine   |
| OpenAI (Chat Model) | Extract invoice ID, parse intent    |
| Google Sheets       | Invoice data source (lookup sheet)  |
| Structured Output Parser | Clean JSON from OpenAI output   |
| HTML Generator      | Custom invoice template (dynamic)   |
| PDF.co              | Converts HTML to PDF                |
| HTTP Request Node   | Downloads the generated PDF         |
| Telegram Send Node  | Sends PDF back to user              |

---

## 🗃️ Google Sheets Format

| invoice_id | client_name | amount | status | date       | email             |
|------------|-------------|--------|--------|------------|-------------------|
| 123        | John Smith  | $150   | Paid   | 2025-07-01 | john@example.com  |

---

## 💬 Example Interaction

**User (via Telegram):**
