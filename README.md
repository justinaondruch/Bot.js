# Bot.js
const TelegramBot = require('node-telegram-bot-api');
const token = process.env.TOKEN;

const bot = new TelegramBot(token, { polling: true });

bot.onText(/\/start/, (msg) => {
    bot.sendMessage(msg.chat.id, "Hello! I'm your Telegram bot.");
});

bot.on('message', (msg) => {
    bot.sendMessage(msg.chat.id, `You said: ${msg.text}`);
});

console.log("Bot is running...");
