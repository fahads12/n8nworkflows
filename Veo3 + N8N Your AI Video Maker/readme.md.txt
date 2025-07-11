🎬 Automated AI Video Generator with Google Veo3 & OpenAI (via n8n)
This n8n workflow automates the process of generating AI-powered videos daily using OpenAI to brainstorm ideas and Google Veo3 for video creation. It also saves all content and video links into Google Sheets for future use.

⚙️ Workflow Breakdown
🔵 1. Provide Topic for Video
▶️ Schedule Trigger
Starts the workflow at a defined time (e.g., daily).

💡 Generate Video Idea
Uses OpenAI Chat Model + Think node to brainstorm a creative and relevant video idea.

Example prompt: “Give a unique video idea in the tech/AI niche.”

🧠 Structured Output Parser
Extracts structured information like title, target audience, theme, or tone from the AI output.

📝 Generate Veo3 Prompt
Refines the idea into a high-quality prompt suitable for video generation using Google's Veo3.

📋 Save Content Information
Logs the generated idea, structured details, and prompt into Google Sheets.

🟣 2. Create a Video & Save Content
🎥 Create Video
Sends the Veo3 prompt to a video generation API (e.g., Fal.ai) via HTTP POST.

⏳ Wait 10 Minutes
Allows time for the video to render and become available for download.

📥 Get Video
Fetches the final video file or URL from the service.

📁 Store the Video
Saves the video URL and metadata (idea, prompt, etc.) into a Google Sheet for easy access.

🧠 Technologies Used
Component	Tool/API
Workflow Engine	n8n
AI Model	OpenAI GPT-4.1
Video Generator	Google Veo3 (via API)
Memory/Thinking	Think Node in n8n
Output Storage	Google Sheets

💬 Prompt Logic (Summarized)
markdown
Copy
Edit
** Step 1: Generate Idea **
→ AI suggests a unique video topic.

** Step 2: Parse Details **
→ Extract structured fields (title, tone, etc.).

** Step 3: Generate Veo3 Prompt **
→ Convert idea into a well-crafted video prompt.

** Step 4: Save & Create **
→ Store idea + prompt, then trigger video generation and store result.
✅ Ideal For
Content creators and marketers automating video production

AI YouTubers & TikTok creators

Automated daily content pipelines

AI video agents using n8n and GPT

