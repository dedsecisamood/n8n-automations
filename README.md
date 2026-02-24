n8n AI Automation Suite
A collection of production-ready n8n workflows designed to automate content repurposing, lead qualification, and customer communication using AI agents (GPT-4o and Llama 3.3).

🚀 What’s Inside?
This repository contains five core automation workflows built to handle business operations without manual intervention:

AI Content Repurposer: Takes one long-form article or URL and automatically turns it into optimized posts for X (Twitter), LinkedIn, Instagram, and WhatsApp. It outputs clean JSON for easy integration.

WhatsApp Lead Qualifier: An AI SDR that chats with leads on WhatsApp. It uses the BANT framework (Budget, Authority, Need, Timeline) to score leads and automatically sends booking links to high-value prospects.

Gmail Auto-Responder: Monitors your inbox, filters out "No-Reply" junk, and uses AI to draft professional replies. It saves the reply as a draft so you can review before hitting send.

Instagram Automation: A scheduled workflow that prepares, filters for quality, and posts content to Instagram automatically.

WhatsApp AI Customer Agent: A 24/7 support agent that can "read" your website links to answer customer questions accurately on WhatsApp.

🛠️ How to Make This Work
Prerequisites
An n8n instance (self-hosted or Cloud).

API Keys for OpenAI (GPT-4o) and Groq (Llama 3.3).

Meta Developer Account for WhatsApp and Instagram Cloud API access.

Google Cloud Console credentials for Gmail/Google Workspace.

Setup Instructions
Import Workflows: Download the .json files from this repo. In n8n, click Workflows > Import from File.

Configure Credentials:

Open each workflow and look for nodes with a key icon (OpenAI, Gmail, WhatsApp).

Click the node and select Create New Credential to paste your API keys.

Set Up Webhooks: For the WhatsApp and Content Repurposer workflows, you will need to copy the "Production Webhook URL" from the Trigger node and paste it into your Meta Developer app or external trigger.

Database (Optional): The Lead Qualifier and WhatsApp Agent use Postgres to remember chat history. If you don't use Postgres, you can swap these for the "Window Binary Memory" node in n8n.

🧐 Technical Analysis
Efficiency & Logic
These workflows aren't just "text generators." They use Conditional Logic and Tool-Calling:

Validation: The JSON Parser node in the Content Repurposer ensures that the AI's output is actually usable by other apps.

Filtering: The Gmail workflow uses a code snippet to instantly kill "Out of Office" or automated emails before they waste your AI tokens.

Memory: By using Postgres Chat Memory, the WhatsApp bots feel human because they remember what a user said three messages ago.

Safety Measures
The 24-Hour Window: The WhatsApp workflows include a check to ensure you stay within Meta’s 24-hour communication window, preventing account bans.

Human-in-the-loop: The Gmail workflow creates Drafts instead of sending emails instantly. This gives you a safety net to prevent AI "hallucinations" from reaching a client.
