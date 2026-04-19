# 🦞 OpenClaw in Codespaces (OC-in-CS)

Welcome to the OpenClaw workshop! This guide will take you from a blank screen to a live AI agent running in your own private cloud environment.

## 🚀 Step 1: Prepare Your Environment

1. **Fork this Repository:** Click the **Fork** button at the top right of this page to create your own copy.
2. **Open in Codespaces:** Click the green **< Code >** button, select the **Codespaces** tab, and click **Create codespace on main**.
3. **Wait for Setup:** VS Code will open in your browser. Wait for the terminal at the bottom to finish initializing.

## 🤖 Step 2: Create Your Bot "Identity"

You need a Telegram bot token to act as the interface for your agent.

1. Open Telegram and search for @BotFather.
2. Send `/newbot` and follow the instructions to name your bot.
3. **Copy the API Token** provided (it looks like `123456:ABC-DEF...`).

## ⚙️ Step 3: Launch the One-Line Installer

Copy and paste this exact command into the VS Code terminal. This downloads OpenClaw and refreshes your terminal settings in one go:

```bash
curl -fsSL https://openclaw.ai/install.sh | bash && source ~/.bashrc
```

*Note: If you still see "command not found" after running this, just open a new terminal tab (click the + icon).*

## 🧠 Step 4: Final Configuration

Now, configure your agent's credentials. Replace the text in quotes with your actual keys:

1. **Set your Telegram Token:**
   ```bash
   openclaw config set providers.telegram.token "PASTE_YOUR_TELEGRAM_TOKEN_HERE"
   ```

2. **Set your Gemini API Key:**
   ```bash
   openclaw config set providers.google.apiKey "PASTE_YOUR_GEMINI_API_KEY_HERE"
   ```
   *(Get your key at aistudio.google.com)*

## ⚡ Step 5: Start Your Agent

Run the gateway to bring your bot to life:
```bash
openclaw gateway run
```

When you see `[telegram] [default] starting provider`, your bot is ready! 

---

### 🧪 Testing Your Bot
* Find your bot on Telegram and say: `Hello! Who are you?`
* Try a search task: `What is the current weather in Singapore?`
* Watch the terminal in Codespaces to see the "Live Reasoning" logs as the agent works.

### 🛠 Quick Fixes
* **To stop the bot:** Press `Ctrl + C`. 
* **To start again:** Type `openclaw gateway run`.
* **Errors:** If the bot doesn't reply, check the terminal for red error messages—this usually means an API key is missing or has extra spaces.
