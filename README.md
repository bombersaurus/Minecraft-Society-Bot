# Bob

A Discord bot written in Java for my friends' server. Bob chats in the `ai-chat` channel or when someone mentions him, using OpenRouter for replies and a folder of text files for context about the server and the group.

It started as my part of a university group project, and I now develop it on my own.

## What it does

- Connects to Discord using JDA
- Replies in an `ai-chat` channel or when directly mentioned
- Keeps short per-channel conversation history
- Loads `.txt` files from a `knowledge` folder for extra context
- Uses Java virtual threads so message handling does not block the bot
- Reads secrets from environment variables

## Why I built it

I wanted a bot my friends could actually talk to, not one that only replies to fixed commands. Getting it to remember the last few messages was the hardest part, because without that every reply ignored the conversation.

## Planned

- Make conversation memory safe when several people message at once
- Per-user cooldowns, tests and CI
- Gaming features for the group, such as Valorant stats lookups

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
mvn exec:java -Dexec.mainClass="io.github.bombersaurus.bob.Main"
```

## Knowledge files

Create a `knowledge` folder in the working directory and add `.txt` files. The bot will combine those files and include them as reference material for replies.

## Notes

No tokens are committed. The bot reads `DISCORD_TOKEN` and `OPENROUTER_API_KEY` from environment variables.
