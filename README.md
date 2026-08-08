# Discord Chatbot

A simple Discord bot built with discord.py that responds to basic greetings and provides useful commands.

## Features

- ✅ Responds to greetings: `hi`, `hello`, `hey`, `yo`
- ✅ Ignores messages from other bots
- ✅ Message Content Intent enabled for full message access
- ✅ Secure token management via environment variables
- ✅ Ready for Railway deployment
- ✅ Ping command to test bot responsiveness
- ✅ Hello command for quick interactions

## Prerequisites

- Python 3.8 or higher
- A Discord bot token from [Discord Developer Portal](https://discord.com/developers/applications)

## Local Setup

1. **Clone the repository:**
   ```bash
   git clone <repository-url>
   cd Dc-bot
   ```

2. **Create a virtual environment:**
   ```bash
   python -m venv venv
   ```

3. **Activate the virtual environment:**
   - On Windows:
     ```bash
     venv\Scripts\activate
     ```
   - On macOS/Linux:
     ```bash
     source venv/bin/activate
     ```

4. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

5. **Set up environment variables:**
   - Copy `.env.example` to `.env`:
     ```bash
     cp .env.example .env
     ```
   - Edit `.env` and add your Discord bot token

6. **Run the bot:**
   ```bash
   python main.py
   ```

## Getting a Discord Bot Token

1. Go to [Discord Developer Portal](https://discord.com/developers/applications)
2. Click "New Application"
3. Go to the "Bot" tab and click "Add Bot"
4. Under the TOKEN section, click "Copy"
5. Paste it in your `.env` file as `DISCORD_BOT_TOKEN`

## Enabling Message Content Intent

The bot has Message Content Intent enabled by default in the code. You also need to enable it in the Discord Developer Portal:

1. Go to your application in the [Discord Developer Portal](https://discord.com/developers/applications)
2. Navigate to the "Bot" tab
3. Scroll down to "Intents"
4. Enable "Message Content Intent"
5. Save changes

## Inviting the Bot to Your Server

1. Go to your application in the [Discord Developer Portal](https://discord.com/developers/applications)
2. Navigate to "OAuth2" → "URL Generator"
3. Select scopes: `bot`
4. Select permissions: `Send Messages`, `Read Messages/View Channels`
5. Copy the generated URL and open it in your browser
6. Select the server and authorize

## Commands

- `!ping` - Check bot latency
- `!hello` - Get a greeting from the bot

## Greetings

The bot automatically responds to these messages:
- `hi`
- `hello`
- `hey`
- `yo`

## Deployment on Railway

### Prerequisites
- GitHub account with the repository
- Railway account (https://railway.app)

### Deployment Steps

1. **Push to GitHub:**
   ```bash
   git add .
   git commit -m "Add Discord bot files"
   git push origin main
   ```

2. **Connect to Railway:**
   - Go to [Railway.app](https://railway.app)
   - Sign in with GitHub
   - Click "New Project"
   - Select "Deploy from GitHub repo"
   - Choose your `Dc-bot` repository
   - Wait for Railway to detect and deploy

3. **Set Environment Variables:**
   - In Railway dashboard, click on your project
   - Go to the "Variables" tab
   - Add new variable: `DISCORD_BOT_TOKEN` = `<your-bot-token>`
   - Railway will automatically restart the service

4. **Monitor Deployment:**
   - Check the "Deployments" tab
   - View logs to confirm the bot is running
   - You should see "Bot has connected to Discord!" in the logs

### Troubleshooting Railway Deployment

**Build fails with Railpack error:**
- Ensure `requirements.txt` is in the repository root
- Check that `python-dotenv` and `discord.py` are listed
- Verify `runtime.txt` specifies `python-3.11`
- Check repository for syntax errors in `.py` files

**Bot doesn't start:**
- Verify `DISCORD_BOT_TOKEN` is set in Railway Variables
- Check bot logs in Railway dashboard
- Ensure bot token is valid and hasn't expired

**Bot offline after deployment:**
- Check Railway logs for error messages
- Verify Discord Developer Portal has Message Content Intent enabled
- Confirm bot still has permissions in your Discord server

## Project Structure

```
Dc-bot/
├── main.py              # Main bot script
├── requirements.txt     # Python dependencies
├── runtime.txt          # Python version specification
├── pyproject.toml       # Project metadata
├── Procfile             # Process definition
├── railway.json         # Railway configuration
├── .env.example         # Example environment variables
├── .gitignore           # Git ignore rules
└── README.md            # This file
```

## Security Notes

- ⚠️ Never hardcode your bot token in the code
- ⚠️ Never commit `.env` file to version control
- ⚠️ Always use environment variables for sensitive data
- ⚠️ Add `.env` to `.gitignore` (already configured)
- ⚠️ Rotate your bot token if accidentally exposed

## License

This project is open source and available for personal use.
