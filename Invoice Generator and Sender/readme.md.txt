# 🧾 Invoice Generator and Sender (n8n Workflow)

This n8n workflow automates the process of generating PDF invoices from Typeform submissions, saving them to Google Drive, and emailing them to users with the invoice attached.

---

## 🔁 Workflow Overview

### Trigger:
- **Typeform Submission** — User fills a form with:
  - Full Name
  - Email Address
  - Product Name
  - Amount Paid

---

### Workflow Steps:

1. **Typeform Trigger**
   - Captures submitted form data via webhook trigger from Typeform.

2. **Function Node**
   - Extracts fields like name, email, product, and amount.
   - Generates a unique invoice number and formatted date.

3. **PDF Generation (PDF.co)**
   - Sends a dynamic HTML invoice to PDF.co API using HTTP POST.
   - Receives a temporary URL to the generated PDF.

4. **PDF Download**
   - Uses HTTP GET to download the PDF file from the returned link.
   - Saves it in binary format (named `Invoice`).

5. **Set Node (Parallel Fork)**
   - Passes all input (including binary) to allow branching into:
     - **Gmail Node**
     - **Google Drive Node**

6. **Gmail Node**
   - Sends an email to the user with a personalized message.
   - Attaches the invoice PDF (`Invoice_{{invoiceNumber}}.pdf`).

7. **Google Drive Node**
   - Uploads the same invoice to a specified folder in Google Drive.
   - Uses dynamic file naming to prevent overwriting:
     - `Invoice_{{name}}_{{invoiceNumber}}.pdf`

---

## 🔧 Technologies Used

| Tool          | Purpose                      |
|---------------|------------------------------|
| Typeform      | User input form              |
| n8n           | Workflow automation          |
| PDF.co        | Convert HTML to PDF invoice  |
| Google Drive  | Store invoice PDF            |
| Gmail (OAuth) | Send email with attachment   |

---

## 📁 File Structure Example (in Google Drive)

