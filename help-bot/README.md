# Matlab-Discord-Bot

A bot for searching commands from Mathworks docs within Discord.

See [help.md](https://bitbucket.org/smcgit/matlab-discord-bot/src/master/msg/help.md) for all commands or type `!help` in chat.

## Installation

Clone this repository (either to your PC or a host). Create a file called `.env` in the root directory, where the token of the bot has to be posted:

```
BOT_TOKEN=<your token here>
NEWS_CHANNEL_ID=<channel ID, where newest Mathworks blog will be posted>
```

Start the bot:

```
node index.js
```

## Structure

Once a message is posted, all regular expressions in the `router` will be tested. If a regular expression is triggered, the function provided via `use` will be applied on the message and the `tokens` from the regular expression.

Usually the bot has to respond with a rendered message. The templates for these messages are in the [msg](https://bitbucket.org/smcgit/matlab-discord-bot/src/master/msg/) directory.

The last regular expression is chosen in a way, that if no command applies, it will search for a template with the name of the command. This way "static" messages can be provided just by creating the template (e.g. `help.md` and `code.md`).

## Credits

Following libraries have been used:

* [cheerio](https://github.com/cheeriojs/cheerio)
* [discord.js](https://github.com/discordjs/discord.js/)
* [dotenv](https://github.com/motdotla/dotenv)
* [mustache.js](https://github.com/janl/mustache.js/)
* [request](https://github.com/request/request)