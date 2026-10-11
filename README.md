# Discord Bot
 
A small Discord bot built with [discord.py](https://discordpy.readthedocs.io/) that I made while practicing Python. It includes a playable Tic Tac Toe game with clickable buttons, where you play against a bot that picks random moves.
 
## Commands
 
| Command   | What it does                                        |
|-----------|-----------------------------------------------------|
| `!ping`   | The bot replies with `pong`                         |
| `!button` | Sends a button that changes color when clicked      |
| `!ttt`    | Starts a Tic Tac Toe game on a 3x3 grid of buttons  |
 
Only the person who started a Tic Tac Toe game can play in it.
 
## Files
 
- `discordBot.py` - the bot, its commands, and the button interfaces
- `game.py` - the game logic (`check_winner` and `is_board_full`)
## Setup
 
1. **Clone the repo**
```
   git clone https://github.com/YOUR-USERNAME/discord-bot.git
   cd discord-bot
```
 
2. **Install dependencies**
```
   pip install discord.py python-dotenv
```
   Or, if you use [uv](https://docs.astral.sh/uv/):
```
   uv add discord.py python-dotenv
```
 
3. **Create a bot and get its token**
   - Go to the [Discord Developer Portal](https://discord.com/developers/applications) and create an application.
   - Open the **Bot** tab and copy the token (use **Reset Token** if needed).
   - On the same tab, turn on **Message Content Intent**. The bot needs it to read commands.
   - Use the **OAuth2** tab to generate an invite link with the `bot` scope and add the bot to your server.
4. **Add your token**
   Create a file named `.env` in the project folder:
```
   DISCORD_TOKEN=your-token-here
```
   No quotes and no spaces around the `=`. The `.env` file is listed in `.gitignore`, so it is never uploaded. Never share your token or commit it.
 
5. **Run the bot**
```
   python discordBot.py
```
   Or with uv:
```
   uv run discordBot.py
```
 
   When it connects, the terminal prints `Logged on as <bot name>`.
 
## Credits
 
Parts of this code were adapted from [SOURCE NAME OR LINK]. Replace this line with where you got the code, and check that its license allows reuse.
 
## License
 
Add a license if you want others to reuse your code, such as the MIT License. GitHub can add one for you when you create a new file named `LICENSE` in the repo.