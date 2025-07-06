# 📄 Resume Collector with AI Summary (n8n Workflow)

Automatically collect resumes from Google Drive, extract candidate information, summarize resumes using OpenAI, and store everything in Airtable.

---

## 🚀 Features

- ✅ Triggered by new resume uploads in Google Drive
- 📄 Extracts text from PDF or DOCX resumes
- 🧠 Summarizes resume content using OpenAI GPT
- 📬 Extracts Name, Email, and Phone using regex
- 📊 Stores all details into Airtable for easy tracking

---

## 🧰 Tools Used

- **Google Drive** – Resume uploads
- **OCR/Text Extraction** – Extract text from resume files
- **OpenAI** – Summarize the resume
- **Airtable** – Store structured candidate data
- **n8n** – Orchestration and workflow automation

---

## 🧩 Workflow Steps

1. **Google Drive Trigger**
   - Monitors a specific folder for new files (PDF/DOCX resumes).

2. **Download File**
   - Fetches the uploaded resume for processing.

3. **Text Extraction**
   - Uses an OCR API or built-in text extractor to get raw text.

4. **OpenAI Summarization**
   - Sends the extracted text to OpenAI (GPT-3.5 or GPT-4) with a custom prompt.
   - Example prompt:
     ```
     Summarize this resume in 3–5 sentences highlighting key skills, experience, and suitability for tech roles:
     {{text}}
     ```

5. **Extract Candidate Info**
   - Extracts name (first line or first non-email line), email, and phone number using JavaScript regex in a Function node.
   - Sample Code:
     ```javascript
     const text = $('Extract from File').first().json.text;
     const email = text.match(/[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-z]{2,}/)?.[0];
     const phone = text.match(/(\+?\d{1,4}[-.\s]?)?\(?\d{3,4}\)?[-.\s]?\d{3,4}[-.\s]?\d{3,4}/)?.[0];
     const lines = text.split('\n').map(l => l.trim()).filter(l => l.length > 0);
     let name = null;
     for (const line of lines) {
       if (!line.includes('@') && !/\d/.test(line)) {
         name = line;
         break;
       }
     }
     return [{ name, email, phone }];
     ```

6. **Send to Airtable**
   - Inserts the extracted data and AI summary into an Airtable table.

---

## 🗃 Airtable Schema

| Field Name   | Type     | Description                     |
|--------------|----------|---------------------------------|
| Name         | Text     | Candidate’s name                |
| Email        | Text     | Candidate’s email address       |
| Phone        | Text     | Candidate’s phone number        |
| Summary      | LongText | AI-generated resume summary     |
| Drive Link   | URL      | Link to original file (optional) |

---

## 📦 Setup Instructions

1. **Create a Google Drive Folder** for uploading resumes.
2. **Connect Google Drive Trigger** in n8n to this folder.
3. **Configure OCR/Text Extraction**
   - Use PDF.co, Cloudmersive, or OpenAI (if structured extraction).
4. **Get OpenAI API Key** and configure the `OpenAI` node.
5. **Create an Airtable Base** and connect via Airtable API key.
6. **Deploy Workflow** in n8n and test by uploading a sample resume.

---

## 📁 Sample Resume

A sample resume is included for testing:  
[John_Doe_Resume.pdf](./John_Doe_Resume.pdf)

---

## 📬 Support

Need help? Open an issue or contact the workflow creator.

---
