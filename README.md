# Bob Bot

Bob Bot is a Java Discord bot that replies in a dedicated study channel or when mentioned. It uses OpenRouter for chat responses and can load local text files as a small knowledge base.

## What it does

- Connects to Discord using JDA
- Replies in an `ai-chat` channel or when directly mentioned
- Keeps short per-channel conversation history
- Loads `.txt` files from a `knowledge` folder for extra context
- Uses Java virtual threads so message handling does not block the bot
- Reads secrets from environment variables

## Why I built it

The goal was to make a practical Discord helper that could answer questions in a casual server without needing a large framework. The code is small enough to understand, but still covers real bot concerns like message intents, API calls, memory, and secret handling.

## Tech

- Java 21
- Maven
- JDA
- OpenRouter API
- Gson

## Setup

Set the required environment variables:

```bash
DISCORD_TOKEN=your_discord_bot_token
OPENROUTER_API_KEY=your_openrouter_key
```

Then build and run with Maven:

```bash
mvn package
mvn exec:java -Dexec.mainClass="com.whale.bot.Main"
```

## Knowledge files

Create a `knowledge` folder in the working directory and add `.txt` files. Bob will combine those files and include them as reference material for replies.

## Notes

This repo does not include tokens or private study files. Keep production secrets in environment variables or your deployment platform's secret manager.
