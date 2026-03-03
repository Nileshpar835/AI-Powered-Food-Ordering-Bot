<!--
Tip: For best results, also add these files to your repo root:
- /assets/demo-telegram.gif
- /assets/workflow-overview.gif
- /assets/architecture.png
- /assets/telegram-chat.png
- /assets/n8n-workflow.png
You can export GIFs from screen recordings (Telegram + n8n) and place them in /assets.
-->

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Poppins&size=26&pause=900&color=22C55E&center=true&vCenter=true&width=900&lines=%F0%9F%8D%BD%EF%B8%8F+AI-Powered+Food+Ordering+Bot;LLMs+%2B+n8n+%2B+Telegram+%2B+Google+Sheets+%2B+Gmail;Real-world+Restaurant+Ordering+Automation" alt="Typing animation" />
</p>

<p align="center">
  <a href="#-live-capabilities">Capabilities</a> •
  <a href="#-architecture-overview">Architecture</a> •
  <a href="#-google-sheets-structure">Sheets</a> •
  <a href="#-setup-instructions">Setup</a> •
  <a href="#-future-improvements">Roadmap</a>
</p>

<p align="center">
  <img alt="Made with n8n" src="https://img.shields.io/badge/n8n-Workflow%20Automation-FF6A00?style=for-the-badge&logo=n8n&logoColor=white" />
  <img alt="OpenAI" src="https://img.shields.io/badge/OpenAI-LLM%20Agent-111827?style=for-the-badge&logo=openai&logoColor=white" />
  <img alt="Telegram" src="https://img.shields.io/badge/Telegram-Bot%20API-229ED9?style=for-the-badge&logo=telegram&logoColor=white" />
  <img alt="Google Sheets" src="https://img.shields.io/badge/Google%20Sheets-Inventory%20%26%20Orders-34A853?style=for-the-badge&logo=google-sheets&logoColor=white" />
  <img alt="Gmail" src="https://img.shields.io/badge/Gmail-Automated%20Emails-EA4335?style=for-the-badge&logo=gmail&logoColor=white" />
</p>

---

# 🍽️ AI-Powered Food Ordering Bot

An intelligent AI-driven restaurant ordering assistant built using **n8n**, **OpenAI**, **Telegram Bot API**, **Google Sheets**, and **Gmail automation**.

This project demonstrates how **LLMs + workflow automation** can create real-world business solutions for restaurants, cloud kitchens, and small food businesses.

---

## 🎬 Demo (Animated)

> Replace the paths below with your actual GIFs/screenshots.

<p align="center">
  <img src="assets/demo-telegram.gif" alt="Telegram ordering demo (GIF)" width="420" />
  <img src="assets/workflow-overview.gif" alt="n8n workflow overview (GIF)" width="420" />
</p>

<details>
  <summary><b>📸 More screenshots</b></summary>
  <br />
  <p align="center">
    <img src="assets/telegram-chat.png" alt="Telegram conversation screenshot" width="420" />
    <img src="assets/n8n-workflow.png" alt="n8n workflow screenshot" width="420" />
  </p>
</details>

---

## 🚀 Live Capabilities

The bot can:

- ✅ Greet customers professionally  
- ✅ Ask for customer name  
- ✅ Show menu dynamically  
- ✅ Take item & quantity  
- ✅ Check inventory from Google Sheets  
- ✅ Confirm order before placing  
- ✅ Store confirmed orders in Google Sheets  
- ✅ Send automated email confirmation (Gmail)  
- ✅ Maintain conversation memory (context-aware)

---

## 🏗️ Tech Stack

- **n8n** – Workflow automation engine  
- **OpenAI (LLM Agent)** – Natural language understanding + structured extraction  
- **Telegram Bot API** – Real-time chat interface  
- **Google Sheets API** – Inventory & orders database  
- **Gmail API** – Automated email confirmations  

---

## 🧠 Architecture Overview

```text
Telegram Trigger
        ↓
AI Agent (OpenAI + Memory)
        ↓
Tools:
   • Inventory (Read Sheet)
   • FAQ (Read Sheet)
   • Orders (Append Sheet)
   • Gmail (Send Confirmation)
        ↓
Telegram Send Message
```

Optional diagram (recommended):

<p align="center">
  <img src="assets/architecture.png" alt="Architecture Diagram" width="900" />
</p>

---

## 📂 Google Sheets Structure

### 1️⃣ Inventory Sheet

| item_name | price | available |
|----------|------:|:---------:|
| Burger   | 120   | yes       |
| Maggi    | 80    | yes       |

### 2️⃣ Orders Sheet

| customer_name | item_name | quantity |
|--------------|-----------|---------:|
| Nilesh       | Burger    | 1        |

---

## 🤖 AI Agent Logic (Behavior Rules)

The AI Agent:

- Collects structured order details (customer_name, item_name, quantity, email if needed)
- Checks **availability** from the Inventory sheet
- Asks for confirmation **before** writing to Orders sheet
- Calls tools **only after confirmation**
- Stores only valid orders (sanity checks: quantity > 0, item exists)
- Sends email using Gmail tool after order is stored
- Replies in short, Telegram-style messages
- Uses memory to keep chat context (user name, last item, last quantity, etc.)

---

## 🔐 Features Implemented

- Conversational memory (context-aware)
- Tool calling with structured arguments
- Inventory validation before confirmation
- Clean order storage logic
- Automated confirmation workflow
- Modular & scalable architecture

---

## 💡 Real-World Use Case

This system can be adapted for:

- Restaurants
- Cloud kitchens
- Small food businesses
- WhatsApp/Telegram ordering systems
- AI-powered customer support & FAQ bots

---

## 🛠️ Setup Instructions

### 1) Clone repository
```bash
git clone git@github.com:Nileshpar835/AI-Powered-Food-Ordering-Bot.git
cd AI-Powered Food Ordering Bot
```

### 2) Import n8n workflow JSON
- Open n8n → **Workflows** → **Import from File**
- Select the provided workflow JSON

### 3) Connect credentials in n8n
Set up these credentials:

- Telegram Bot Token
- OpenAI API Key
- Google Sheets OAuth
- Gmail OAuth

### 4) Update Google Sheet IDs
- Replace sheet IDs / ranges used by:
  - Inventory Read
  - FAQ Read (optional)
  - Orders Append

### 5) Activate workflow
- Switch workflow to **Active**
- Start chatting with your Telegram bot

---

## 📈 Future Improvements

- Payment gateway integration (UPI/Stripe/Razorpay)
- Multi-language support
- Dynamic menu management UI
- Admin dashboard for order analytics
- WhatsApp integration
- User order history + repeat order support

---

## 👨‍💻 Author

**Nilesh Parmar**  
AI / ML Engineer | Automation Developer  
Building real-world AI systems with LLMs.

---

## ⭐ If You Like This Project

Give it a **star** ⭐ and connect with me on LinkedIn!

---

## 📌 Notes

- This repo is intended as a practical demonstration of **LLM agents + automation**.
- For production use:
  - add rate limiting,
  - stronger validation,
  - audit logs,
  - secrets management,
  - and monitoring.
