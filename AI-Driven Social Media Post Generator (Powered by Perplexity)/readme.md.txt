🚀 AI-Driven Social Media Post Generator (Powered by Perplexity)
This automated workflow generates, designs, and publishes engaging social media content using AI tools like OpenAI, Perplexity, and image generation models — then publishes across multiple platforms.

📊 Overview
This system:

Researches content ideas using advanced AI.

Generates engaging text and corresponding visuals.

Publishes content across multiple social platforms.

Tracks posts in Google Sheets for analytics and logging.

🧠 Workflow Breakdown
1. Creating & Researching
Schedule Trigger: Initiates the workflow on a scheduled interval.

Create an Idea AI Agent: Uses LLMs to brainstorm and refine post topics.

OpenAI Chat Model: For core content structure.

Perplexity: For real-time research and facts.

Think Module: Handles complex logical flows.

Structured Output Parser: Formats the AI output.

Append Row in Sheet: Logs idea generation step in Google Sheets.

Graphic Idea AI Agent: Enhances visual ideas for post graphics.

2. Generate Images
Generate Image: Text-to-image prompt generation.

Convert to File: Converts base64 to file.

Get Image URL: Uploads image and retrieves link.

Edit Fields: Prepares post for final publishing.

3. Publish on Different Social Media
Upload to Backend: Distributes content via API to:

Instagram

TikTok

Facebook

LinkedIn

Pinterest

4. Save to Google Sheet
Done Node: Updates the Google Sheet with final status.

🧩 Tech Stack
OpenAI GPT: For content and caption generation.

Perplexity AI: For research-driven insights.

Image Generator API: For post visuals.

Social Media APIs: For direct publishing.

Google Sheets: For tracking and logs.

✅ Benefits
End-to-end automation from ideation to publishing.

Reliable and fact-checked content using Perplexity.

Multi-platform distribution without manual effort.

Great for marketing teams, influencers, and brand managers.

📌 Use Cases
Daily content generation for social media calendars.

Research-based educational/informative posts.

Visual storytelling via AI-generated artwork.

📎 Diagram Legend
🟫 Brown: Content creation and research.

🟦 Blue: Visual generation pipeline.

🟥 Red: Social media publishing nodes.

🟨 Yellow: Data logging and Google Sheet updates.