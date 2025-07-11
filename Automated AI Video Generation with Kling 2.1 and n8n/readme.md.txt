🤖 Automated AI Video Generation with Kling 2.1 and n8n
This workflow automates the end-to-end process of generating, assembling, and publishing AI-powered videos using Kling 2.1, OpenAI, and n8n. It’s designed to generate social-ready content and distribute it across multiple platforms like TikTok, YouTube Shorts, and Facebook.

✨ Key Features
🧠 Generates both image and video prompts using OpenAI

🖼️ Creates stunning AI images

🎬 Uses Kling 2.1 to convert images to video

📤 Publishes videos on TikTok, YouTube Shorts, and Facebook

📊 Tracks progress and stores logs in Google Sheets

🔁 Runs on a scheduled basis for consistent content output

🧩 Workflow Overview
1. Creating Prompts
Schedule Trigger – Starts the flow at set intervals.

Image Prompt AI Agent – Uses OpenAI to generate a prompt for image creation.

Video Prompt AI Agent – Uses OpenAI to create the script or theme for video.

Structured Output Parsers – Convert AI output into structured formats for downstream steps.

Set Status – Updates Google Sheet with the prompt generation status.

2. Create Image
Create Image – Sends the generated image prompt to an AI image API.

Wait 1 Minute – Waits for the image to render.

Get Image – Retrieves the rendered image.

3. Image-to-Video with Kling 2.1
Create Video with Kling 2.1 – Sends image to Kling 2.1 API for video generation.

Wait 2 Minutes – Allows processing time.

Get Video – Downloads the finished video.

4. Prepare Content
Get Video URL – Prepares video asset link.

Save Information – Appends video data (URLs, status, etc.) into Google Sheets.

Upload to Bicto.io – Optional: Upload video to a hosting service (e.g., Bicto or alternative).

5. Publish on Different Social Media
TikTok – Posts the video to TikTok via API.

YouTube Shorts – Publishes on YouTube as a short video.

Facebook – Shares video to a Facebook page.

LinkedIn – Deactivated by default but ready for enterprise publishing.

🛠️ Requirements
Tool/API	Purpose
OpenAI	Prompt generation
Kling 2.1 API	Image-to-video rendering
Google Sheets	Status logging and prompt tracking
TikTok API	Video publishing
YouTube Data API	YouTube Shorts uploading
Facebook API	Publishing to Facebook pages/groups
n8n	Automation platform

📦 Use Cases
🧵 Social media automation for creators and marketers

📢 Brand awareness campaigns through AI-generated reels

📚 Educational or motivational short videos

🧠 Thought-leadership content with automated visuals and publishing