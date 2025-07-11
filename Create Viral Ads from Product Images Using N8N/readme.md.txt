📢 Create Viral Ads from Product Images Using n8n
This workflow automates the process of transforming product submissions into viral ad creatives and sending them directly to Telegram, using the power of OpenAI, Google Sheets, and Cloudinary.

🚀 Workflow Highlights
📥 Collects product ideas from form submissions

☁️ Uploads submitted images to Cloudinary

📊 Stores and retrieves idea metadata via Google Sheets

🎨 Uses OpenAI to create ad creatives from product data

📲 Sends generated ads to a Telegram channel/group

🔁 Fully automated and scalable via looping logic

🧩 Workflow Structure
🔷 Get Ideas with Form Submission & Google Sheets
On Form Submission

Triggers when a user submits a form (e.g., product idea submission).

Upload Image

Uploads submitted image to Cloudinary.

POST: https://api.cloudinary.com/...

Get Rows in Sheet

Reads product information from a connected Google Sheet.

🔶 Create Ads & Send to Telegram
Loop Over Items

Iterates through each idea entry retrieved from Google Sheets.

Get Image

Retrieves Cloudinary image for the current loop item.

Create Image

Uses OpenAI image generation API to create an ad creative.

POST: https://api.openai.com/...

Convert to File

Converts base64 string output into a file for Telegram.

Telegram Node

Sends the generated ad creative to Telegram via sendDocument.

If Condition (Optional)

Logic check to control or branch the message logic (e.g., based on category, campaign, etc.).

🔧 Tools & Services Used
Tool/Service	Purpose
n8n	Workflow automation
Google Sheets	Storing form data
Cloudinary	Hosting uploaded product images
OpenAI	Generating ad creatives from data
Telegram	Delivering ads to a chat/channel

📌 Use Cases
Automated ad design pipeline for e-commerce

Rapid prototyping of visual marketing content

Scalable Telegram marketing system for products or offers

Internal creative idea validation system

🛠️ Setup Requirements
Google Sheet connected to form submission

Cloudinary account with API credentials

OpenAI API Key

Telegram Bot Token and chat/group ID

n8n instance (self-hosted or cloud)

