# 🚀 Telegram post submission bot

Submit WordPress posts directly via Telegram! This plugin enables authorized Telegram users to create WordPress posts step-by-step through a simple chatbot interface. More information https://omidakhavan.blog/front-end-wordpress-submission-telegram-bot/

---

### 🧩 Features

- **Interactive Telegram session flow** for creating WordPress posts.
- **Step-by-step wizard**: title → tags → category → content → publish.
- **Only authorized Telegram user IDs** can submit posts.
- Posts are saved as **draft** for editorial control.
- New categories are **automatically created** if they don’t exist.
- Smart **keyboard menu** for `/post`, `/endsession`, and `/start`.

---

### 📦 Installation

1. Clone or download the plugin into your `wp-content/plugins/` directory.
2. Run `composer install` to load dependencies.
3. Create a `.env` file in the plugin root:

TELEGRAM_BOT_TOKEN=your_telegram_bot_token

TELEGRAM_AUTHORIZED_USERS=12345678,87654321

4. Activate the plugin in WordPress admin.
5. Set your Telegram bot webhook to the REST endpoint:
https://your-site.com/wp-json/telegram/v1/webhook/

---

### 🧪 How It Works

Once the bot receives `/start` from an authorized user:
1. It shows a custom keyboard with `/post` and `/endsession`.
2. The user is prompted step-by-step to enter:
   - **Title**
   - **Tags**
   - **Category**
   - **Content**
3. When the user types `publish`, the plugin:
   - Validates the inputs.
   - Inserts a new WordPress post as **draft**.
   - Sends back the permalink.
   - Clears the session (via transient).

---

### 🔒 Security

- Only user IDs listed in `TELEGRAM_AUTHORIZED_USERS` can use the bot.
- Inputs are sanitized using WordPress-native functions.
- No persistent sessions — uses transients with a 1-hour expiration.

---

### 🛠️ Requirements

- **PHP**: 8.0.2+
- **WordPress**: 5.8+
- Composer dependencies:
  - `irazasyed/telegram-bot-sdk`
  - `vlucas/phpdotenv`
