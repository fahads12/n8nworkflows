🎬 End-to-End Viral Video Builder for YouTube
The End-to-End Viral Video Builder for YouTube is a fully automated n8n workflow that transforms video ideas into fully produced and published content. From prompt generation to video rendering and final YouTube upload, this workflow streamlines the entire content creation lifecycle using AI tools and APIs.

🚀 Key Features
🧠 AI-powered idea-to-script generation (OpenAI)

📄 Structured content prompt parsing

🎼 Intro music & background audio integration

🎞️ Video generation via external API (e.g., JSON2Video)

📺 Automated YouTube publishing

🧾 Google Sheets-based logging and error tracking

⏱️ Runs on a schedule (no manual work required)

🧩 Workflow Sections
📋 Video Idea & Prompts
Schedule Trigger – Starts the workflow on a recurring schedule (e.g., daily).

Get row(s) in sheet – Retrieves video ideas from Google Sheets.

OpenAI Chat Model – Generates engaging prompts and video outlines.

Structured Output Parser – Parses the AI output into a format ready for rendering.

🎵 Take Intro Video & Music
Get Music – Pulls music and intro assets from your Google Sheet.

🛠 Generate a Video
HTTP Request – Sends prompt + assets to the video rendering API.

Wait – Allows time for the video to be processed.

HTTP Request1 – Retrieves the generated video URL for publishing.

⚠️ Error Handling (Fallback)
Switch + Wait1 – Checks if the video generation failed and retries after a delay.

Error Log – Writes error data to Google Sheets for review.

📢 Publish Your Created Video
Get Video – Fetches the final video and prepares metadata.

HTTP Request2 – (Optional) Final processing, thumbnails, or metadata enrichment.

YouTube Upload – Publishes the video to your connected YouTube channel.

Done – Updates the Google Sheet marking the task as completed.

🛠️ Requirements
Tool	Purpose
OpenAI	Prompt and script generation
Google Sheets	Idea sourcing, metadata, logging
Video API	Video rendering (e.g., JSON2Video)
YouTube API	Uploading videos programmatically
n8n	Workflow automation platform

📌 Use Cases
Daily YouTube Shorts automation

Faceless content production pipelines

Educational, motivational, or storytelling video creation

Scalable content strategy for creators & marketers

📂 Optional Enhancements
Add ElevenLabs for voiceovers

Use Runway or Pictory for alternative video rendering

Integrate Google Drive or Dropbox for file backup

Add Discord/Telegram notifications on publish

