🎞️ Automated Viral Shorts Production with n8n + Hailuo AI
This workflow uses n8n, OpenAI, Cloudinary, and Hailuo AI to automatically create and store viral short-form videos (e.g., YouTube Shorts, TikToks, Reels). With a scheduled trigger, it generates prompts, creates images, converts them into videos, and logs all outputs in Google Sheets.

🚀 Workflow Overview
✅ Automated Tasks
🧠 Generate creative prompts using OpenAI Chat Model

🖼️ Create AI-generated images based on the prompts

🎬 Convert images into videos using Hailuo AI

☁️ Upload images to Cloudinary

📊 Save video links and metadata to Google Sheets

📌 Workflow Sections
1. Create Prompt
Trigger: Scheduled via Schedule Trigger (e.g., daily).

Action:

Uses the OpenAI Chat Model to generate a visual or storytelling prompt.

Sends the structured prompt to the image generation module.

2. Generate Image
Create Image: Sends prompt to OpenAI’s image generation endpoint (https://api.openai.com/...).

Convert to File: Converts base64 output to a usable file format.

Upload Image: Uploads the image to Cloudinary for hosting and reuse.

3. Image to Video
Image to Video: Sends the image to Hailuo AI’s video generation endpoint (https://queue.fai.run/...).

Wait 10 Minutes: Allows sufficient time for video rendering.

Get Video: Fetches the completed video URL from Hailuo.

4. Save Information in Google Sheets
Save Information: Appends the video link, image link, and prompt data into a Google Sheet for tracking and analytics.

🧠 Tools Used
Tool	Purpose
OpenAI	Prompt and image generation
Cloudinary	Image hosting
Hailuo AI	Convert images into stylized videos
Google Sheets	Store logs and video metadata
n8n	Automation engine for full orchestration

🛠️ Requirements
✅ OpenAI API key

✅ Cloudinary account and API credentials

✅ Hailuo AI endpoint access

✅ Google Sheets integration in n8n

✅ Active n8n (Cloud or Self-Hosted)

📈 Use Cases
Automated creation of YouTube Shorts or TikToks

Generative art videos for social media

Viral quote videos or visual storytelling

Hands-free content pipeline for agencies or creators