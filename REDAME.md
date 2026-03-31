# 🛒 Flipkart-Style E-commerce Newsletter Automation (n8n)

## 🚀 Project Overview

This project is a **mini e-commerce automation system** built using **n8n**.
It simulates a Flipkart-style newsletter that automatically fetches product deals and sends them to **Slack** and **Telegram**.

⏱️ The workflow runs on a **scheduled trigger (daily automation)** — no manual work needed.

---

## 🎯 Features

* 🔄 Automated daily execution (Schedule Trigger)
* 📦 Fetch products from API (no Google Sheets)
* 🔥 Filter best deals (discount > 20%)
* 📰 Generate newsletter-style message
* 📩 Send notifications to:

  * Slack
  * Telegram
* ⚡ Lightweight and beginner-friendly

---

## 🧠 Workflow Architecture

```
Schedule Trigger
      ↓
HTTP Request (Fetch Products API)
      ↓
Format Data (Function Node)
      ↓
Filter Deals (>20% Discount)
      ↓
Generate Newsletter
      ↓
Send to Slack + Telegram
```

---

## 📦 Example Output

```
🔥 Today's Best Deals

🛍️ Product Name
💰 Price: ₹5000
🏷️ Discount: 30%
👉 Link
```

---

## ⚙️ Setup Instructions

### 1️⃣ Import Workflow

* Open n8n
* Go to **Workflows**
* Click **Import**
* Paste the JSON workflow

---

### 2️⃣ Configure Schedule Trigger

* Select **Schedule Trigger**
* Set:

  * Interval: Daily
  * Time: 09:00 AM

OR use cron:

```
0 9 * * *
```

---

### 3️⃣ Setup Slack Integration

* Create a Slack App
* Enable Bot Token
* Add permission:

  * `chat:write`
* Install the app
* Copy Bot Token

👉 In n8n:

* Open Slack node
* Add credentials using Bot Token
* Set channel (e.g. `#general`)

---

### 4️⃣ Setup Telegram Integration

#### Create Bot

* Open Telegram
* Search **BotFather**
* Run:

```
/newbot
```

#### Get Bot Token

* Copy the token

#### Get Chat ID

* Send message to bot
* Open:

```
https://api.telegram.org/bot<YOUR_BOT_TOKEN>/getUpdates
```

* Copy:

```
chat.id
```

👉 In n8n:

* Add Telegram credentials
* Paste Bot Token
* Enter Chat ID in node

---

## 🧪 How It Works

* Workflow runs automatically every day ⏱️
* Fetches latest products 🛒
* Filters best deals 🔥
* Sends formatted newsletter 📩

---

## ❗ Common Errors & Fixes

### ❌ Telegram: “chat not found”

* Make sure bot is started
* Use correct Chat ID (number)
* Send at least one message to bot

---

### ❌ Slack not sending

* Check bot is added to channel
* Verify permissions (`chat:write`)

---

## 🚀 Future Improvements

* 📸 Add product images
* 👥 Multi-user notifications
* 🤖 AI-generated descriptions
* 🛒 Real Flipkart scraping
* ⏱️ Smart scheduling (only new deals)

---

## 🛠️ Tech Stack

* n8n (workflow automation)
* Slack API
* Telegram Bot API
* DummyJSON API (product data)

---

## 👨‍💻 Author

Kumar K

---


* ⭐ Star your repo
* 🚀 Build more automations with n8n
