Telegram Post Bot

A WordPress plugin to submit posts via Telegram. This is a starter template for demonstration purposes and is free to use. Proceed with caution if using it in production environments.

Features

Receive and process messages from Telegram

Authenticate users before accepting post submissions

Create WordPress posts from Telegram messages

Supports post title, tags, category, and content submission

Getting Started

Clone the Repository

git clone https://github.com/yourusername/Telegram-Post-Bot.git
cd Telegram-Post-Bot

Install Dependencies

Make sure you have Composer installed, then run:

composer install

Create the .env File

Duplicate the .env.example file and set up your bot credentials:

cp .env.example .env

Edit .env and add:

TELEGRAM_BOT_TOKEN=your_telegram_bot_token
TELEGRAM_AUTHORIZED_USERS=your_telegram_user_id (comma-separated for multiple users)

Activate the Plugin

Copy the Telegram-Post-Bot folder into your WordPress wp-content/plugins/ directory.

Activate it from the WordPress admin panel under Plugins.

Setting Up the Webhook

Set up your Telegram bot webhook to point to your WordPress REST API:

https://yourwebsite.com/wp-json/telegram/v1/webhook/

Use the following command to set the webhook:

curl -X POST "https://api.telegram.org/botYOUR_BOT_TOKEN/setWebhook?url=https://yourwebsite.com/wp-json/telegram/v1/webhook/"

Usage

Start a chat with your bot and send /start to initiate the process.

Follow the prompts to submit a post.

Posts will be saved as drafts in WordPress.

Notes

This is a starter template for demonstration and testing purposes. Ensure proper security measures before using it in production environments.

For more details, check out the full guide on my blog.
