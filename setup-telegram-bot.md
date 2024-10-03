# Telegram Bot Setup Guide <!-- by LAEY 0xpH -->

This guide will walk you through the steps to create a Telegram bot using BotFather, retrieve the bot token, and find the `chat ID` and `message thread ID`.

---

## 1. Create a Telegram Bot via BotFather

1. Open Telegram and search for **[BotFather](https://t.me/botfather)**.
2. Start a chat with BotFather by clicking the **Start** button or sending `/start`.
3. Create a new bot by sending the command `/newbot`.
4. Follow the instructions provided by BotFather:
   - **Choose a name** for your bot (this can be anything).
   - **Choose a username** for your bot. The username must be unique and must end with `bot` (e.g., `myawesomebot`).
5. After successfully creating the bot, BotFather will send you a message with the **bot token**:

   Save this **bot token** as it will be needed for making API requests.

---

## 2. Get Your Chat ID

### Option 1: Using a Web Browser

1. Open the following URL in your web browser, replacing `YOUR_BOT_TOKEN` with the token you got from BotFather:
   ```
   https://api.telegram.org/botYOUR_BOT_TOKEN/getUpdates
   ```
2. Send a message to your bot from your personal Telegram account or a group where the bot is added.
3. Refresh the URL, and you will see a JSON response. Find the section that looks like this:
   ```json
   "chat": {
     "id": 123456789,
     "first_name": "YourName",
     "username": "yourusername"
   }
   ```
4. The value of `id` is your **chat ID**.

### Option 2: Using a Telegram Bot

1. Add your bot to a group or channel.
2. Send a message in the group or channel.
3. Use the same URL as above and check the JSON response to find the chat ID.

---

## 3. Get Your Message Thread ID

The `message thread ID` is useful for replying to messages in a thread. It is typically available in the context of a group chat or channel where threads are used. To find it:

1. Follow the same steps to get updates from your bot.
2. Look for the messages where the `message_thread_id` is present:
   ```json
   "message_thread_id": 12345
   ```
3. The value is your **message thread ID**.

---

## Conclusion

You have now successfully created a Telegram bot, retrieved your bot token, chat ID, and message thread ID. You can use this information to interact with the Telegram Bot API.
