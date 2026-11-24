# Discord Bot
 
A small Discord bot built with [discord.py](https://discordpy.readthedocs.io/) that I made while practicing Python. It includes a playable Tic Tac Toe game with clickable buttons, where you play against a bot that picks random moves.
 
## Features
 
- **Game mode:** Single player. You play X against the bot, which plays O and picks a random open square each turn.
- **Interaction method:** A 3x3 grid of Discord buttons. Click a square to make your move.
- **Color-coded board:** Empty squares are grey, your X is blue, and the bot's O is red.
- **Private games:** Only the player who started a game can click its board. Anyone else sees a private "This isn't your game!" message.
- **Results:** The bot announces a win, a loss, or a tie, then locks the board.
- **Extras:** A `!ping` health check and a `!button` demo that changes color when clicked.

## Prerequisites
 
- Python 3
- [discord.py](https://pypi.org/project/discord.py/)
- [python-dotenv](https://pypi.org/project/python-dotenv/)
- A Discord account and a server where you can add a bot
## Setup
 
### 1. Create the bot in the Discord Developer Portal
 
1. Go to the [Discord Developer Portal](https://discord.com/developers/applications) and create a **New Application**.
2. Open the **Bot** tab and copy the bot token. Treat it like a password and never commit it.
3. On the same tab, enable **Message Content Intent**. The bot needs it to read `!` commands.
### 2. Invite the bot to your server
 
In **OAuth2 > URL Generator**, select the `bot` scope and the permissions listed under [Required Bot Permissions](#required-bot-permissions). Open the generated URL and choose your server.
 
### 3. Install and run
 
```bash
git clone https://github.com/MatthewS1803/discord-bot.git
cd discord-bot
pip install discord.py python-dotenv
```
 
Create a file named `.env` in the project folder:
 
```
DISCORD_TOKEN=your_token_here
```
 
Make sure `.env` is listed in `.gitignore`, then start the bot:
 
```bash
python discordBot.py
```
 
If you use [uv](https://docs.astral.sh/uv/), run `uv run discordBot.py` instead. A "Logged on as" message in the terminal means the bot is connected.
 
## Commands
 
| Command   | What it does                                        |
|-----------|-----------------------------------------------------|
| `!ttt`    | Starts a Tic Tac Toe game against the bot           |
| `!button` | Sends a demo button that turns green when clicked   |
| `!ping`   | Replies `pong` to check that the bot is responsive  |
 
## How to Play
 
1. Type `!ttt` in a channel the bot can see.
2. Click any empty square to place your X.
3. The bot answers by placing an O in a random open square.
4. The first to get three in a row (across, down, or diagonal) wins. If the board fills up first, it's a tie.
5. Games stop responding after about 3 minutes of inactivity (the default for Discord button views). Type `!ttt` again to start a new game.
## Required Bot Permissions
 
The code does not define a permission set, so grant the bot at least these in the channels where it will run:
 
- View Channels
- Send Messages
- Read Message History
Buttons are message components and need no extra permission.
 
## Project Structure
 
| File             | Purpose                                                  |
|------------------|----------------------------------------------------------|
| `discordBot.py`  | Bot setup, commands, and button interfaces               |
| `game.py`        | Game logic (`check_winner`, `is_board_full`)             |
| `.env`           | Your bot token (create this yourself, do not commit it)  |
 
## License

This project is licensed under the MIT License. See

## Credits
 
- Built with [discord.py](https://github.com/Rapptz/discord.py) and [python-dotenv](https://github.com/theskumar/python-dotenv).
- CodeDex: Build a Discord Bot With Python(https://www.codedex.io/projects/build-a-discord-bot-with-python)
