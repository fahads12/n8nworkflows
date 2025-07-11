📧 AI-Powered Gmail Organizer
This n8n workflow uses OpenAI to intelligently classify incoming Gmail messages and respond automatically. It streamlines email handling by extracting relevant information, categorizing messages, and sending replies — all without manual intervention.

🧠 Key Features
✅ Automatically triggered when a new email is received

🤖 Uses OpenAI to extract and understand email content

🗂️ Classifies emails into predefined categories (Services, Consultations, Payments, Others)

✉️ Sends context-aware replies based on classification

🔄 Fully automated with clean, modular flow

🔁 Workflow Structure
1. Gmail Trigger
Function: Detects when a new email is received in your Gmail inbox.

Action: Initiates the workflow.

2. Information Extractor
Function: Parses the email to extract key fields like subject, sender, and body content.

3. OpenAI Chat Model (Summarizer)
Function: Enhances or summarizes the email content for better understanding and processing.

4. Conditional Branch (if Node)
Function: Determines whether extracted data is valid or needs manual adjustment.

✅ True → Route to Edit Fields

❌ False → Route to alternate Edit Fields

5. Edit Fields (Manual Override)
Function: Allows optional manual correction or modification of extracted data.

6. Merge Node
Function: Merges both paths (True/False) back into a single flow.

7. Clean Data
Function: Cleans and prepares the data for classification.

🏷️ Email Classification
8. Text Classifier (OpenAI Chat Model)
Function: Classifies emails into one of the following categories using AI:

Services Request

Consultation Requests

Payments

Others

📤 Auto-Response Actions
Depending on the classification, the email is routed to the appropriate Gmail action node that:

Adds a label to the email

Sends an automated reply tailored to the category

Responses Include:
✅ Services Requests → Reply to services requests

💬 Consultation → Reply to consultation requests

💸 Payments → Reply to payment-related questions

📦 Others → Generic or fallback response

📌 Requirements
Gmail account with n8n Gmail credentials

OpenAI API key for using ChatGPT

n8n self-hosted or cloud instance

🔒 Notes
Ensure your Gmail and OpenAI credentials are securely stored in n8n.

Customize reply messages inside the appropriate Gmail reply nodes.

Extendable to handle more categories by modifying the classifier prompt and branching.

🧩 Use Cases
Customer service inbox automation

Lead generation triaging

Internal support ticket classification

General productivity improvement