# 🦞 OpenClaw in Codespaces (OC-in-CS)

Welcome to the OpenClaw workshop! This guide will take you from a blank screen to a live AI agent running in your own private cloud environment.

## 🚀 Step 1: Prepare Your Environment

1. **Fork this Repository:** Click the **Fork** button at the top right of this page to create your own copy.
2. **Open in Codespaces:** Click the green **<> Code** button, select the **Codespaces** tab, and click **Create codespace on main**.
3. **Wait for Setup:** VS Code will open in your browser. Wait for the terminal at the bottom to finish initializing.

## 🤖 Step 2: Create Your Bot "Identity"

You need a Telegram bot token to act as the interface for your agent.

1. Open Telegram and search for [@BotFather](https://t.me/botfather).
2. Send `/newbot` and follow the instructions to name your bot.
3. **Copy the API Token** provided (it looks like `123456:ABC-DEF...`).

## ⚙️ Step 3: Configure OpenClaw

In the VS Code terminal, run the following commands one by one:

1. **Install OpenClaw:**
   ```bash
   npm install -g openclaw
   ```

2. **Initialize the Config:**
   ```bash
   openclaw init
   ```
   *Follow the prompts. When it asks for your Telegram token, paste the one you got from BotFather.*

3. **Set the AI Brain (Gemini):**
   ```bash
   openclaw config set providers.google.apiKey "YOUR_GEMINI_API_KEY"
   ```
   *(Get your key at [aistudio.google.com](https://aistudio.google.com))*

## ⚡ Step 4: Launch the Agent

Run the gateway to start your bot:
```bash
openclaw gateway run
```

When you see `[telegram] [default] starting provider`, your bot is alive!

## 🧪 Step 5: Test the Agent

1. Go to Telegram and find the bot you created.
2. Send it a message: `Who are you?`
3. Try a search: `Search for the latest news on AI agents.`
4. Watch the terminal in Codespaces—you will see the "thoughts" of the agent as it processes your request in real-time.

---

### 🛠 Troubleshooting for Learners

* **Bot not responding?** Check if you see `[telegram] message received` in your terminal. If not, double-check your Bot Token.
* **API Errors?** Ensure your Gemini API key is valid and you have "pay-as-you-go" or free-tier credits available.
* **Terminal stuck?** Press `Ctrl + C` to stop the process and run `openclaw gateway run` again.
* **Clean Start?** If things get messy, run `killall node` to clear the terminal (note: this may cause the Codespace to refresh).
