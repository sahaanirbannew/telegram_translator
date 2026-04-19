# 🌍 Telegram Seamless Translator Bot
Anirban Saha
April 2026
www.anirbansaha.com

A Python-based Telegram bot powered by **Telethon** and **LLM** integration that automatically translates incoming and outgoing private messages in real-time.

## 🚀 Features

* **Bidirectional Translation:** Automatically translates messages you receive into English and messages you send into the recipient's preferred language.
* **Dynamic Language Detection:** Uses an LLM to detect the language of incoming text and saves user preferences to a local CSV database.
* **Context-Aware AI:** Leveraging LLM capabilities for high-quality, natural-sounding translations rather than rigid literal translations.
* **Automatic Edits:** For outgoing messages, the bot automatically edits your sent message to the translated version.

---

## 🛠️ Tech Stack

* **Language:** Python
* **Library:** [Telethon](https://docs.telethon.dev/) (MTProto API)
* **AI Model:** LLM API (DeepSeek compatible)
* **Data Storage:** Pandas (CSV-based user persistence)

---

## 📋 Prerequisites

1.  **Telegram API Credentials:** Obtain your `API_ID` and `API_HASH` from [my.telegram.org](https://my.telegram.org).
2.  **LLM API Key:** Obtain an API key from your chosen LLM provider.
3.  **Python Environment:** Ensure you have Python 3.8+ installed.

---

## 🔧 Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/telegram-translation-bot.git
   cd telegram-translation-bot
   ```

2. **Install dependencies:**
   ```bash
   pip install telethon httpx pandas
   ```

3. **Configuration:**
   Update the configuration variables in the script with your actual credentials:
   ```python
   API_ID = 1234567               # Your API ID
   API_HASH = "your_hash"         # Your API Hash
   DEEPSEEK_KEY = "your_api_key"  # Your LLM API Key
   ```

---

## 🖥️ How It Works

### 1. Incoming Messages
When a contact sends you a message in a foreign language:
* The bot detects the language using an LLM request.
* It checks the `user_db.csv` to see if the user’s base language is already recorded.
* It responds with a translated version (prefixed with 🇮🇳 EN:).

### 2. Outgoing Messages
When you send a message:
* The bot identifies the recipient's language from the local database.
* It translates your text into their detected language via the LLM.
* It **edits** your original message to the translated text instantly.

---

## ⚠️ Important Notes

* **Session Management:** On the first run, the script creates a `session_name.session` file. Keep this file secure as it contains your login credentials.
* **Metadata Validation:** The bot uses a strict JSON format to prompt the LLM for language detection to ensure data integrity.
* **CSV Database:** User IDs and their detected languages are stored in `user_db.csv` for persistence across sessions.

---

## 📄 License
This project is open-source and available under the MIT License.
