📰 Daily AI-Powered Finance News Summarizer via Telegram
This n8n workflow fetches the latest finance-related news every day at 10 AM, summarizes the top 15 articles using GPT-4.1, and sends a clean summary directly to Telegram. It also stores the summaries in Google Sheets for record-keeping.

🔁 Workflow Overview
1. Trigger Every Day at 10 AM
Starts the automation daily at 10:00 AM.

2. Get the Most Recent Articles
GNews API – Fetches latest finance-related news articles.

NewsAPI – Retrieves financial updates from global sources.

Map Nodes – Standardizes and extracts relevant fields (title, description, url, etc.).

Merge Node – Combines articles from both sources into a single dataset.

3. Produce Summarized Content and Send on Telegram
AI News Summarizer (GPT-4.1)

Filters and selects top 15 finance-related articles.

Summarizes each article in 1–2 concise sentences.

Prepends today’s date ({{ $now.format('yyyy/MM/dd') }}) to each summary.

Includes article links for further reading.

Limits the response to 2000 characters in plain text (no extra formatting).

Save to Google Sheets

Stores each day’s summary for logging and analysis.

Send Summary to Telegram

Delivers the compiled summary to a Telegram chat via the Bot API.

🔧 Technologies Used
n8n (Open-source workflow automation)

GNews API and NewsAPI (for fetching articles)

OpenAI GPT-4.1 (for AI summarization)

Google Sheets (for logging)

Telegram Bot API (for delivery)

🧠 Prompt Instructions for Summarizer
mathematica
Copy
Edit
** Select Top Articles **
From {{$json.articles}}, choose the 15 most relevant articles related to finance advancements, tools, research, and applications.

** Summarize Clearly **
Write in clear, professional, and readable language, summarizing the main point of each article in 1–2 short sentences.

** Include Links **
After each summary, add the article's URL for readers to explore more.

** Add the Date **
Begin the summary with today’s date:
{{ $now.format('yyyy/MM/dd') }}

** Output Format **
Return only the plain text summary — avoid any extra formatting or explanations. Limit the response to a maximum of 2000 characters.
✅ Use Case
Perfect for financial analysts, investors, fintech communities, or anyone who wants a quick, AI-curated summary of the latest financial developments — delivered straight to Telegram.