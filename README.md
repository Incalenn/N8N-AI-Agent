# AI Agent (n8n Workflow)  
**Date:** 06/04/2025  
**Author:** PHAM Van Alenn  

---

## 📌 Introduction  

As AI continues to evolve, its integration into automation platforms like **n8n** unlocks new possibilities. From AI-enhanced customer service to autonomous research assistants, these tools reshape how we can interact with digital environments.

In this project, I showcase an **AI Agent powered by OpenAI, Telegram, and Gmail**, operating seamlessly within an **n8n workflow**. The agent not only responds to text and voice messages sent via Telegram, but also leverages tools like **Gmail** and **OpenAI’s Chat Model** to carry out intelligent, multi-modal actions.

### 🔹 Why n8n?  

**n8n** is a powerful node-based automation platform—offering flexibility, visual workflow design, and deep integrations without writing complex code. It makes building AI-enabled automations intuitive and scalable.

---

## 🎯 Project Overview  

This workflow implements a **Telegram-integrated AI Agent** that can:

- Transcribe **voice messages** using OpenAI Whisper.  
- Understand and respond to **text inputs** using GPT-4.  
- Trigger **Gmail** operations (send/read emails).  
- Provide **smart, AI-powered responses** via Telegram using natural language understanding.  

It blends voice processing, AI inference, messaging automation, and email tools into a seamless AI-powered interaction pipeline.

---

![Workflow Diagram](./images/AlennWorkFlowN8N.png)

## ⚙️ Workflow Logic

### 🔄 Flow Breakdown:

1. **Telegram Trigger**  
   Captures incoming messages from Telegram (either text or voice).

2. **Switch Node**  
   Detects message type:  
   - If **text**, it goes directly to be formatted.  
   - If **voice**, it fetches the file and transcribes it.

3. **Telegram (get: file)**  
   Downloads the user’s voice message (audio file).

4. **OpenAI (Transcribe Recording)**  
   Uses OpenAI’s Whisper model to **convert voice to text**.

5. **Edit Fields**  
   Standardizes the input (from either text or voice) to feed into the AI Agent.

6. **AI Agent (n8n Tools Agent Node)**  
   - Connected to:  
     - **OpenAI Chat Model** (GPT-4o or GPT-3.5)  
     - **Gmail Get Many** (fetch emails)  
     - **Gmail Send** (send AI-generated emails)  
   - Acts as the **intelligent decision-maker**, invoking tools based on user intent.

7. **Telegram (SendMessage)**  
   Sends the AI’s final response (or action feedback) back to the user.

---

## 🛠️ Utilized Technologies  

| Technology / Service | Purpose |
|----------------------|---------|
| **n8n**              | No-code/low-code automation orchestration |
| **Telegram Bot**     | Front-end user interface (text/voice input/output) |
| **OpenAI Whisper**   | Voice-to-text transcription |
| **OpenAI GPT-4 / GPT-3.5** | AI reasoning and natural language understanding |
| **Gmail (Send & Get)** | Email interaction tools |
| **AI Agent Node (n8n)** | Coordinates reasoning and tool invocation |

---

## 🧠 AI Agent Capabilities  

- 🗣️ **Voice Understanding** – Converts voice to text for natural conversation.  
- 🧠 **Language Comprehension** – Uses GPT-4 to understand complex queries.  
- 📩 **Email Actions** – Reads or sends emails through Gmail.  
- 🤖 **Multimodal Interaction** – Accepts both voice and text, outputs via Telegram.

---

## 🏆 Milestones  

### ✅ Setup Telegram Bot Integration  
- Connected via Telegram Trigger & Messaging nodes.  
- Supports text and voice messages.

### ✅ Voice Transcription  
- Implemented **OpenAI Whisper** integration.  
- Seamless switch between voice and text logic.

### ✅ AI Reasoning Agent  
- Configured **OpenAI Chat Model** for language understanding.  
- Wrapped within **AI Agent Toolset Node**.

### ✅ Gmail Tools Integration  
- Used Gmail nodes to **fetch** and **send** messages via AI commands.  
- Agent can respond to queries like "Check my latest email" or "Send a reply."

### ✅ Final Integration  
- Responses sent back via Telegram, maintaining conversational flow.

---

## ⚠️ Challenges & Considerations  

- **Latency in transcription** – Voice-to-text can add a small delay.  
- **Telegram rate limits** – Must be handled to avoid blocking.  
- **Sensitive data** – Ensure API keys and user info are secured.  
- **Contextual memory** – Currently session-based; long-term memory not yet implemented.

---

## 🚀 Getting Started  

### 🔹 1. Install & Configure n8n  
Use [n8n cloud](https://n8n.io) or self-host via Docker.  

### 🔹 2. Set Up Telegram Bot  
Create a bot using [BotFather](https://core.telegram.org/bots#botfather), get the token, and connect it to your **Telegram Trigger** node.

### 🔹 3. Add API Keys  
Set OpenAI and Gmail credentials in **n8n Credentials Manager**.  

### 🔹 4. Deploy Workflow  
Import the workflow into your n8n instance and activate it.  

---

## 🔮 Future Enhancements  

✅ **Memory integration** – Add short-term context memory with vector embeddings.  
✅ **Notion / Google Sheets Tools** – Let AI manage documents/spreadsheets.  
✅ **Scheduled Tasks** – Trigger AI actions at intervals.  
✅ **Multi-language Support** – Use `Translate` tool for wider accessibility.  

---

## 🎓 Conclusion  

This n8n AI Agent Workflow demonstrates how low-code platforms can be paired with powerful AI tools to create **interactive, voice-enabled, and action-driven automations**.

From reading your emails to holding natural conversations, the AI Agent is a step toward autonomous digital assistants that interact with users just like a human would.

It was a very rich and horizon-expanding subject to dig my hands in. I think I'd like to polish it furthermore and add Google Calendar and plenty other tools of the same type.

---

## 📬 Contact  
🔹 **GitHub**: [github.com/Incalenn](https://github.com/Incalenn)  
🔹 **LinkedIn**: [linkedin.com/in/vanalennpham](https://www.linkedin.com/in/vanalennpham/)
