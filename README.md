# 🛡️ Edit-Guardian — Telegram Protection Bot

*__**Edit-Guardian** is a modular Telegram protection bot built to keep your groups safe, smart, and automated.__*  
**It uses multiple plugin modules to handle group moderation, anti-abuse protection, auto-deletion, imposter detection, and admin automation.**

_> Built with Python — fully modular, configurable, and ready for deployment._

---

![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)
![Contributions](https://img.shields.io/badge/Contributions-Welcome-brightgreen.svg)

---

## 🔍 Overview

**__Edit-Guardian is designed for **Telegram group protection**.__**
**__Each protection feature is isolated inside its own plugin under the `Anonymous/plugins/` directory, making it easy to enable, disable, or extend features without touching core code.__**

---

## 🧩 Plugin Breakdown

Here’s what each major plugin does:

- **`admins.py`** – Admin-only commands (ban, unban, promote, mute, etc.)  
- **`auto-approve.py`** – Auto-approve system for new members  
- **`auto-delete.py`** – Automatically deletes unwanted or restricted content  
- **`autoimage.py`** – Image moderation / enhancement (integrated with Real-ESRGAN)  
- **`bcast.py`** – Developer-only broadcast system  
- **`detect_abuse.py`** – Filters messages for abuse, spam, or banned words (`blacklist.txt`, `words.txt`)  
- **`devs.py`** – Developer & sudo command utilities  
- **`game.py`** – Fun and engagement games  
- **`imposter.py`** – Detects cloned usernames or fake users pretending as admins  

---

## ⚙️ Configuration

**All configuration (API tokens, MongoDB, etc.) is managed in:**

**Anonymous/config.py**

_Open this file and set the following variables:_

```python
API_ID = "your_api_id"
API_HASH = "your_api_hash"
BOT_TOKEN = "your_bot_token"

# Optional: MongoDB or database connection
MONGO_URL = "your_mongo_connection_string"

# Other optional configuration:
# OWNER_ID, SUDO_USERS, LOG_CHANNEL, etc.

> You can customize database, logging, and filter settings directly in config.py.
```


---

## 🧠 Core Features

🧩 Modular plugin-based structure

🚫 Abuse & spam word detection

🕵️ Imposter and fake user detection

👮‍♂️ Admin command utilities

🔄 Auto message cleanup and join approvals

💬 Global broadcast system

🎮 Optional mini-games

💾 MongoDB integration for persistent storage



---

## 🗂️ Project Structure

```bash
Edit-Guardian/
│
├── Anonymous/
│   ├── __main__.py           # Bot entry point
│   ├── bot.py                # Core logic
│   ├── config.py             # Main configuration (edit here)
│   ├── database/             # Data storage handlers
│   ├── helpers/              # Utility and support functions
│   └── plugins/              # Protection and feature modules
│
├── requirements.txt          # Python dependencies
├── Dockerfile / Procfile     # Deployment configuration
├── LICENSE                   # License file
└── README.md                 # You are here 😄

```
---

## 🛠️ Installation

1️⃣ Clone the repository

```bash
git clone https://github.com/hasnainkk-07/Edit-Guardian.git
cd Edit-Guardian
```
2️⃣ Install dependencies

```bash
pip install -r requirements.txt
```
3️⃣ Edit configuration

```Open Anonymous/config.py and set:

API_ID, API_HASH, BOT_TOKEN

Optional: MONGO_URL, OWNER_ID, LOG_CHANNEL
```

4️⃣ Run the bot

```bash
python3 -m Anonymous
```

---

## ☁️ Deployment

Edit-Guardian supports Heroku, or Docker deployment out-of-the-box.

For Heroku → use Procfile

For Docker → build using Dockerfile



---

## 🔧 Plugin Control

Plugins are located in /Anonymous/plugins/.
You can enable or disable them easily:

Disable a plugin: Rename the file (e.g. auto-delete.py → auto-delete.py.disabled)

Enable again: Rename back to .py

Optionally, you can manage plugin loading via the plugin loader (if included in __main__.py).



---

## 📜 Commands (Examples)

_> Actual command names depend on plugin code. These are typical examples:_



start - To check bot is alive
new - Start a new word guessing game
end - End the current game
addword - (Bot Admin) Add a word to the list
delword - ( Bot Admin) Remove a word from the list
checkword - Check if a word exists in the bot's word list
leaderboard - View the global leaderboard
permit - (Admin) Permit a user to bypass restrictions
rpermit - (Admin) Remove a user from the permitted list
permitlist - (Admin) List all permitted users
protection - (Admin) Toggle protection for edited messages
help - Show all commands


---

## ⚠️ Tips

Grant the bot admin permissions (delete, ban, pin, invite) for proper functionality.

Keep your tokens and Mongo credentials private.

Edit blacklist.txt and words.txt regularly for up-to-date abuse filtering.
