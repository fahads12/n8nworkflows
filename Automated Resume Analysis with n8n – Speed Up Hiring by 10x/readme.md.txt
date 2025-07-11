📄 Automated Resume Analysis with n8n – Speed Up Hiring by 10x
This n8n workflow automates the process of receiving, analyzing, and storing resumes, enabling HR teams to evaluate candidates faster and more effectively. With AI-powered extraction and evaluation, the workflow drastically reduces manual effort and speeds up hiring decisions by up to 10x.

🚀 Features
📥 Auto-fetch resumes from Gmail

☁️ Upload & download from Google Drive

📄 Extract text from PDF resumes

🤖 Use AI (OpenAI) to evaluate and score candidates

📝 Edit extracted fields manually if needed

📊 Save results in Google Sheets for easy access and tracking

🔧 Workflow Breakdown
1. Inputting Resumes
(Red Section)
Automates the collection and extraction of resumes.

Gmail Trigger: Watches for new emails with resume attachments.

Upload File: Saves the attachment to Google Drive.

Download File: Retrieves the uploaded file.

Extract from File: Extracts text content from the PDF resumes.

2. Extract Information & Evaluate the Candidates
(Blue Section)
Processes and evaluates the resume using AI.

Information Extractor: Parses relevant fields (name, skills, experience).

AI Agent (OpenAI Chat Model 2): Evaluates and scores the candidate based on predefined hiring criteria.

Edit Fields: Allows optional manual editing of the AI-generated fields.

Code Node: Formats the data for Google Sheets.

3. Save Data
(Green Section)
Stores processed data in a spreadsheet.

Append Row in Sheet: Adds the candidate’s information and score to a Google Sheet.

🧠 Benefits
Reduce manual screening time.

Gain AI-powered insights into candidate strengths.

Centralize candidate data for easy comparison.

Improve response time and hiring efficiency.

📌 Requirements
n8n (self-hosted or cloud)

Google Account with:

Gmail Access

Google Drive

Google Sheets

OpenAI API Key (for AI evaluation)

🔄 Setup Instructions
Clone or recreate the workflow in your n8n instance.

Configure the following nodes:

Gmail trigger (OAuth credentials)

Google Drive (upload/download)

Google Sheets (append)

OpenAI (API key in AI Agent node)

Customize the AI prompt for evaluation criteria (skills, experience, etc.).

Deploy and monitor resume inflow and AI evaluations in real-time.

📚 Example Use Case
A tech recruiter receives dozens of resumes daily. This workflow automatically:

Extracts each resume's content,

Evaluates candidates based on required skills (e.g., Python, Java),

Logs all results in a spreadsheet,

Notifies the recruiter to review top-scoring candidates.

📈 Result
By automating the resume screening process, your recruitment pipeline becomes faster, smarter, and more scalable – giving you an edge in hiring top talent.