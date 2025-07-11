🌐 Smart Web Data Research Bot
This automation sets up a powerful AI research assistant that performs real-time Google searches, scrapes web pages, and returns summarized answers using GPT-4.

Ideal for answering complex queries using the most recent web data.

🧠 What This Bot Can Do
✅ Real-Time Web Research
Accepts a chat-based question

Generates a relevant Google search using Serper API

Scrapes key sources using a web crawler

Feeds cleaned content to GPT-4

Returns a summarized response and highlights

🔁 Workflow Breakdown
plaintext
Copy
Edit
[Trigger: When Chat Message Received]
          ↓
[AI Agent] ← Memory (Window Buffer)
     ↓
[SERP Search Engine]
     ↓
[Search URL Preparation]
     ↓
[Clean URL]
     ↓
[HTTP Request to Serper]
     ↓
[Parse Search Results]
     ↓
[Web Crawler → Clean Text → OpenAI Summary]
🛠 Stack & Tools
Tool	Role
n8n	Orchestration + logic control
OpenAI GPT-4	Summarizes search results into readable insights
Serper API	Converts queries to real-time Google search
Web Crawler	Extracts HTML content from links
Window Buffer Memory	Maintains conversation context
Google Search Tool	Optional fallback for SERP

🧩 Use Case Examples
User Query	Bot Output
“What’s the latest on EU AI regulation?”	Summary from top sources like TechCrunch, Wired, etc.
“Compare iPhone 15 vs Galaxy S24 reviews”	Condensed review comparison with source links
“Who won the latest NBA finals?”	Real-time score + article summaries
“Top AI conferences 2025”	Curated list with dates, links, and organizer names

⚙️ How to Set Up
Step 1: Clone or Import Workflow
Log in to your n8n account

Download and import the provided .json workflow file

Step 2: Connect APIs
OpenAI API Key (for GPT-4)

Serper API Key (from serper.dev)

Google Search API (optional)

Optional: Use your own web crawler tool or keep the default

Step 3: Customize Parameters
Modify the GPT prompt style for tone/formality

Adjust search depth or result limits

Set up fallbacks (e.g. use Google Search if SERP fails)

🧠 AI Agent Capabilities
Understands context (via buffer memory)

Adapts to query type (fact vs opinion vs summary)

Returns structured output (bullet points, sources, highlights)

Can cite original source links if enabled

🌟 Features
Feature	Enabled
Multi-turn memory	✅
Citation generation	✅
Web scraping & cleanup	✅
Modular search logic	✅
Google Calendar link parsing	✅

