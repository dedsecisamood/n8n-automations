# n8n AI Automation Suite

A collection of **production-ready n8n workflows** designed to automate content repurposing, lead qualification, and customer communication using AI agents (GPT-4o and Llama 3.3).  

These workflows combine **AI intelligence, automation, and human-first design** to streamline business operations without manual intervention.

---

## 🚀 What's Inside?

This repository includes **five core AI workflows**:

### 1️⃣ AI Content Repurposer
- Converts a single long-form article or URL into optimized posts for **X (Twitter), LinkedIn, Instagram, and WhatsApp**.  
- Outputs structured JSON for seamless integration with other apps.  
- Ensures content is **engaging, platform-specific, and ready-to-post**.

### 2️⃣ WhatsApp Lead Qualifier
- AI-powered SDR that chats with leads on **WhatsApp**.  
- Qualifies leads using the **BANT framework** (Budget, Authority, Need, Timeline).  
- Automatically sends booking links to high-value prospects.  

### 3️⃣ Gmail Auto-Responder
- Monitors your inbox, filters out "No-Reply" and automated emails.  
- Drafts professional replies using AI and saves them in Gmail drafts for review.  
- Ensures **human-in-the-loop** to prevent mistakes.  

### 4️⃣ Instagram Automation
- Automatically prepares, filters, and posts content to **Instagram**.  
- Maintains consistent posting schedule with minimal supervision.  

### 5️⃣ WhatsApp AI Customer Agent
- 24/7 AI support agent for **WhatsApp**.  
- Reads website links to answer customer questions accurately.  
- Keeps conversation history to respond naturally and human-like.

---

## 🛠️ How to Set Up

### Prerequisites
- An **n8n instance** (self-hosted or cloud).  
- API Keys for **OpenAI (GPT-4o)** and **Groq (Llama 3.3)**.  
- **Meta Developer Account** for WhatsApp & Instagram Cloud API.  
- **Google Cloud Console credentials** for Gmail/Google Workspace.  

### Setup Instructions
1. **Import Workflows**  
   - Download `.json` files from this repo.  
   - In n8n, go to `Workflows > Import from File`.  

2. **Configure Credentials**  
   - Open each workflow node with a key icon (OpenAI, Gmail, WhatsApp).  
   - Click `Create New Credential` and paste your API keys.  

3. **Set Up Webhooks**  
   - For WhatsApp and Content Repurposer workflows, copy the "Production Webhook URL" from the Trigger node.  
   - Paste it into your Meta Developer app or external trigger.  

4. **Database (Optional)**  
   - Lead Qualifier and WhatsApp Agent use **Postgres** to remember chat history.  
   - If Postgres is unavailable, replace it with the `Window Binary Memory` node in n8n.

---

## 🧐 Technical Analysis

### Efficiency & Logic
- **Validation:** JSON Parser node ensures AI outputs are usable for other apps.  
- **Filtering:** Gmail workflow discards automated emails to save AI tokens.  
- **Memory:** WhatsApp workflows use Postgres Chat Memory to maintain natural, human-like conversations.  

### Safety Measures
- **24-Hour Window Compliance:** WhatsApp bots check Meta’s 24-hour messaging window to prevent account issues.  
- **Human-in-the-Loop:** Gmail drafts give you a chance to review AI responses before sending, preventing errors or “hallucinations.”

---

## 📈 Why This Suite Works
- **Full automation:** Reduces manual workload while maintaining human-level quality.  
- **Platform-aware:** Content is optimized for Twitter/X, LinkedIn, Instagram, and WhatsApp.  
- **Human-first AI:** Conversations and emails feel natural and professional.  
- **Production-ready:** All workflows are tested, JSON-ready, and easy to deploy.

---

## ⚡ Get Started
Created by DEDSEC
