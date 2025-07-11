🛰️ AI-Powered Lead Generation Agent
Google Maps + Perplexity Sonar API + GPT + Google Sheets

This AI agent automates local lead generation by combining Google Maps data, Perplexity's Sonar API, and OpenAI to source, enrich, and structure business contact details into Google Sheets — making outreach-ready data available in minutes.

🧠 What This Agent Can Do
🔍 Search Google Maps
Extracts local business data like name, phone, website, address, hours, and reviews using the Serper-powered Maps API.

🧾 Save Data to Google Sheets
Automatically stores structured business data into a connected Google Sheet.

📩 Enrich Leads via Perplexity's Sonar API
Fetches deeper company insights, including emails, background data, and more.

🧹 Clean & Format Results
Uses OpenAI to clean and structure results into outreach-ready records.

⚡ Trigger-based Execution
Kicks off on a new row added to the sheet or on chat message received — ideal for automated workflows.

🛠 Tools & APIs Used
Tool	Function
🔹 Google Maps API (via Serper)	Searches local businesses
🔹 Perplexity Sonar API	Fetches enriched company data
🔹 Google Sheets	Stores and updates lead data
🔹 OpenAI GPT-4	Parses and structures messy data
🔹 n8n	Workflow automation & orchestration

🧱 Workflow Breakdown
💬 Chat Agent Trigger (Top Section)
plaintext
Copy
Edit
User Message → AI Agent → Decide Action
    ├─ OpenAI Chat Model (intent recognition)
    ├─ Store to Google Sheet (maps data)
    └─ Map Searcher (via Serper API)
📍 Local Business Scraper via Google Maps
plaintext
Copy
Edit
Trigger: Chat or User Input
↓
Call Serper (Google Maps API)
↓
Extract business data: name, address, phone, website, etc.
↓
Append to Google Sheet
🔍 Enrich Lead via Perplexity API
plaintext
Copy
Edit
Trigger: New row added in Google Sheet
↓
Filter valid businesses
↓
Loop over businesses
↓
Call Perplexity API with business name/domain
↓
Parse JSON response
↓
Update existing row with email and company insights
📄 Save Output Workflow
plaintext
Copy
Edit
Trigger → Parse Data → Append Row → Confirm Response
🧪 Getting Started
Sign up / log into n8n

Import this workflow

Set up credentials:

Serper API (Google Maps)

Perplexity API key

OpenAI API key

Google Sheets OAuth

Create or link a Google Sheet with appropriate column headers

Run and test: Add a business manually or trigger via chat


📊 Ideal Use Cases
Local SEO agencies targeting nearby businesses

B2B SaaS lead scraping & enrichment

Automated outreach data pipelines

Google Maps-based prospecting

🔒 Notes
Respect Google Maps & LinkedIn Terms of Service

Rate-limit API usage for stability and compliance

Validate emails before outreach using additional tools like NeverBounce or ZeroBounce