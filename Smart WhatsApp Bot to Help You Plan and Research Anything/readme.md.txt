🤖 Smart WhatsApp Bot to Help You Plan and Research Anything
This project sets up an intelligent WhatsApp bot using n8n, AI chat models, and real-time search tools. It allows users to message a bot on WhatsApp to instantly receive well-formatted plans, recommendations, or research—no manual Googling required!

🚀 Key Features
📲 WhatsApp-based user interaction

💬 AI-powered planning and conversational responses

🔍 Automated real-time research using SerpAPI

📦 Sends structured results back to WhatsApp

🧠 Uses context-aware memory to keep conversations flowing naturally

🧠 Workflow Overview
1. WhatsApp Input From User
(Green Block – Input)

WhatsApp Trigger: Starts the workflow when a user sends a message.

2. Plan as Per User Input
(Red Block – AI Planning)

WhatsApp Bot Planner:

Uses Groq Chat Model for fast, intelligent response generation.

Leverages Window Buffer Memory to maintain conversation context.

3. Research Agent
(Red Block – Research)

Research Agent:

Powered by OpenAI Chat Model for deeper reasoning.

Integrated with SerpAPI for real-time search and data gathering.

4. Sending Well Formatted Plan to WhatsApp
(Green Block – Output)

Send Message Node: Formats and sends the final plan or research result back to the user on WhatsApp.

⚙️ Requirements
n8n

WhatsApp Business API / Twilio or similar (to connect WhatsApp)

OpenAI API key (for AI chat)

Groq API key (optional for fast inference)

SerpAPI key (for live search)

✅ Use Cases
🧳 Travel Itinerary Planning

🍽 Restaurant & Recipe Recommendations

🧑‍💻 Career/Job Advice

📚 Academic Research Help

🛍️ Shopping Suggestions

🧠 Quick Facts or Summarized Knowledge

🛠 Setup Instructions
Deploy the workflow in your n8n instance.

Connect your WhatsApp API provider.

Configure API credentials:

OpenAI

Groq

SerpAPI

Customize the Planner Prompt to guide the AI response style.

Test the workflow by messaging your bot!

💡 Benefits
Available 24/7 to answer or plan anything

Real-time internet-powered research

Friendly, natural conversation via WhatsApp

Great for businesses, students, and general productivity