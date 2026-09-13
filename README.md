# Minecraft Society Bot

A Discord bot written in Java that chats with members of a Minecraft society server. It answers in the `ai-chat` channel or when someone mentions it, using OpenRouter for replies and a folder of text files for server specific info.

## Team project

This was my part of a university group project. Each of us built bot features on our own, then we merged them into one bot for the society's server. I built the AI chat: the OpenRouter calls, the knowledge base and the chat memory. The merged team bot is here: [Discord-Bot-Group-Project](https://github.com/impossibleiman/Discord-Bot-Group-Project).

## What it does

- Connects to Discord using JDA
- Replies in an `ai-chat` channel or when directly mentioned
- Keeps short per-channel conversation history
- Loads `.txt` files from a `knowledge` folder for extra context
- Uses Java virtual threads so message handling does not block the bot
- Reads secrets from environment variables

## Why I built it

I wanted members to be able to ask the bot questions about the server and get a proper answer, not just a fixed command reply. Getting it to remember the last few messages was the hardest part, because without that every reply ignored the conversation.

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

Create a `knowledge` folder in the working directory and add `.txt` files. The bot will combine those files and include them as reference material for replies.

## Notes

No tokens are committed. The bot reads `DISCORD_TOKEN` and `OPENROUTER_API_KEY` from environment variables.
