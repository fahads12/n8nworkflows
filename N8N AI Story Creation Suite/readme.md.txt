🎬 N8N AI Story Creation Suite
The N8N AI Story Creation Suite is a powerful automation workflow that generates complete multimedia stories using GPT-4o, RunwayML, and ElevenLabs. From a single user prompt, the suite creates images, converts them into video, generates voiceover audio, and stores everything for future use.

🧠 Key Features
🗣️ Accepts a chat prompt and uses GPT-4o to generate story content

🖼️ Transforms text into AI-generated images using OpenAI's image model

🎞️ Compiles images into a video using RunwayML

🔊 Converts story text into speech with ElevenLabs and uploads audio to Google Drive

📥 Logs all content into a spreadsheet for easy access and reuse

⚙️ Workflow Structure
1. Generate Prompt
Trigger: Starts when a new chat message is received.

Action: Uses OpenAI GPT-4o to craft a creative or narrative prompt for story generation.

2. Create Images Using GPT-4o Image Generation API
Tool: OpenAI image generation endpoint.

Purpose: Generates images based on the story prompt.

API: https://api.openai.com/...

3. Convert Images to Video Using Runway
Tool: RunwayML API

Steps:

Generate Video: Sends images to Runway to be turned into a video.

Wait 90 Seconds: Gives time for video generation to complete.

Get Video: Retrieves the completed video from Runway.

API: https://api.dev.runway...

4. Generate and Retrieve Audio via ElevenLabs & Google Drive
Tool: ElevenLabs API

Steps:

Generate Audio: Converts the story prompt or script into speech.

Upload File: Uploads the audio file to Google Drive for storage.

API: https://api.elevenlabs.io/...

5. Save Content
Purpose: Stores all metadata (prompt, video/audio links, generation time) into a Google Sheet for tracking.

Action: Uses the Get Content node to append data to a spreadsheet.

🧩 Technologies Used
Tool/Service	Purpose
OpenAI GPT-4o	Text generation & image generation
RunwayML	Image-to-video generation
ElevenLabs	Text-to-speech audio creation
Google Drive	File storage for audio
Google Sheets	Storing metadata and logs
n8n	Workflow orchestration

🔐 Requirements
OpenAI API key (GPT-4o)

RunwayML API key

ElevenLabs API key

Google account with Drive and Sheets access

Self-hosted or Cloud n8n instance

📦 Use Cases
AI Storytelling / Book Creation

Educational animated video generation

Content automation for YouTube Shorts, TikTok, etc.

Multimodal storytelling projects

