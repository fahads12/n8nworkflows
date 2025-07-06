# 📄 Tax Filing Document Collector – n8n Workflow

This workflow helps collect tax documents from clients via a webhook, uploads the received file to Google Drive, and sends a confirmation email with a checklist reminder.

---

## 🚀 Workflow Summary

### 📥 1. Webhook Node – Receive Client Submission

- Triggered via `POST` request (e.g. from Postman or a front-end form).
- Accepts:
  - `name` (text)
  - `email` (text)
  - `docListExpected` (text, array-like string)
  - `data0` (uploaded document – PDF, JPG, etc.)

📌 **Binary Field Name**: `data0`

---

### ☁️ 2. Google Drive Node – Upload the File

- Uploads the incoming file to a specific folder in your Google Drive.
- Filename format includes client name and timestamp to prevent overwrites.

📁 **Folder**: `/TaxDocs/{{ $json.name }}`  
📄 **File Name**: `{{ $json.name }}_{{ $now }}_{{ $binary.data0.fileName }}`  
📦 **Binary Property**: `data0`

---

### ⚙️ 3. Set Node – Prepare Email Content

Extracts and formats required fields for use in the email.

Fields set:
- `name`: `{{ $json.name }}`
- `email`: `{{ $json.email }}`
- `uploadedFileName`: `{{ $binary.data0.fileName }}`
- `docListExpected`: `["ID", "Salary Slip", "Investment Proof"]`

---

### 📧 4. Email Node – Send Checklist Email

Sends a confirmation email to the client with the uploaded filename and a list of required documents.

**To**: `{{ $json.email }}`  
**Subject**: `Your Tax Document Submission Checklist`  
**Body**:
```html
Hi {{ $json.name }},<br><br>
We received your file: <strong>{{ $uploadedFileName }}</strong>.<br><br>
Please ensure you've also uploaded:<br>
- ID<br>
- Salary Slip<br>
- Investment Proof<br><br>
We'll follow up later if anything is missing.<br><br>
Thanks,<br>
TaxBot
