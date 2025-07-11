🤖 LinkedIn AI Agent for B2B Prospecting
This AI-powered automation streamlines LinkedIn lead generation using Apify, Findymail, and OpenAI GPT. It intelligently extracts and analyzes data from LinkedIn, including:

Prospect names and job titles

LinkedIn profiles

Company details

Verified professional emails

It’s designed to be affordable, scalable, and efficient, unlike expensive LinkedIn tools charging fixed fees or per-result pricing.

🚀 What This Agent Can Do
🔎 Find LinkedIn profiles for individuals and companies

🧠 Analyze LinkedIn profile and company data

📬 Retrieve verified contact emails using Findymail

🧾 Organize and summarize data using GPT-4

⚙️ Integrate into your CRM or outbound email flow

🔁 Workflow Overview

[When Chat Message Received]
         ↓
[LinkedIn Agent]
   ├── Uses OpenAI for prompt interpretation
   ├── Uses Apify to scrape LinkedIn search results
   ├── Retrieves:
   │   ├── Prospect LinkedIn URL
   │   ├── Prospect Details
   │   ├── Company LinkedIn URL
   │   ├── Company Details
   │   └── Prospect Email (via Findymail)
   ↓
[Return Structured Lead Profile]

🧱 How It Works
1. Receive a User Query
The user asks for information about a person or company. Example:

arduino
Copy
Edit
"Find me the LinkedIn profile and email for Sarah Jones, CMO at Canva."
2. Search LinkedIn Profiles via Apify
The workflow uses Apify's Google Search Scraper to target only LinkedIn URLs, improving accuracy and avoiding irrelevant search results.

3. Scrape Profile or Company Page
Once a profile or company page is found, Apify extracts:

Name, job title, summary, location

Experience & education

Company name, size, industry

Social/contact info

4. Find Verified Emails (Optional)
Using Findymail, the workflow can fetch and validate professional emails tied to the profile.

5. Summarize & Return Results
The AI agent processes and returns the data in a structured, human-readable format. You get all key insights instantly.

💰 Why Use This Agent?
Feature	Typical Tools	This Workflow
Cost	$25+/month + per result	~$5 for 1000 results (Apify)
Free Tier	❌	✅ $5 free from Apify
GPT-Powered	❌	✅
Customizable	❌	✅ Full n8n access

🛠 Tools & APIs Used
Tool	Purpose
OpenAI GPT-4	Understanding and summarizing results
Apify	Scraping Google/LinkedIn profile and company pages
Findymail	Verifying professional email addresses
n8n	Orchestration and automation platform
Window Buffer Memory	Maintains conversation context

🧪 Getting Started
Sign up for n8n

Import the LinkedIn Agent template

Add credentials for:

OpenAI

Apify (free credits available)

Findymail

Test with a sample query

Customize to match your sales flow or CRM

🔧 Customize & Expand
📩 Connect with tools like HubSpot, Pipedrive, Mailchimp

📊 Auto-score leads using GPT or Zapier

🎯 Filter by title, location, or industry

🔁 Run recurring LinkedIn searches via schedule

🔒 Notes on Usage
LinkedIn scraping may violate their TOS. Use responsibly.

For privacy-first workflows, consider local storage and opt-outs.

Apify provides proxy management to reduce scraping bans.

