# 🦁 RexCord Starter Kit

Template repo for **The RexCord Initiative**, a free Discord bot workshop for
Rex Mundi students, taught by alumni as a Bina Nusantara University
community service project.

Full schedule, sign-up and parent info: **(HERE)[https://rexcord.jomontolalu.com/]**

**In the workshop?** Click **Use this template → Open in a codespace** above,
then follow Part A below. Everything runs in the browser — nothing to install.

**Just browsing?** This is a beginner discord.py curriculum in 6 modules:
commands → personality/randomness → message events → web APIs & embeds →
polls/permissions → an interactive minigame. `bot_complete.py` has every
module fully commented; `bot.py` is the blank starting point students build
into.

---

## Part A: Create your bot on Discord (10 min)

1. Go to **discord.com/developers/applications** → **New Application** → give it a cool name.
2. Left menu **Bot** → **Reset Token** → **Copy**. Discord only shows it once, so paste it into `.env` right away (Part B).
3. Still on **Bot**, scroll to **Privileged Gateway Intents** → turn ON **Message Content Intent** → **Save Changes**.
4. Left menu **OAuth2** → **URL Generator**
   - Scopes: ✅ `bot`
   - Bot permissions: ✅ Send Messages ✅ Embed Links ✅ Add Reactions ✅ Read Message History ✅ Manage Messages
   - Copy the URL at the bottom, open it, and add the bot to **your own test server**.

## Part B: Run your bot (5 min)

1. Open the `.env` file (it's already there) and paste your token. No quotes, no spaces:
   ```
   DISCORD_TOKEN=your-token-here
   ```
2. In the terminal at the bottom of the screen, type:
   ```
   python bot.py
   ```
3. See `✅ ... is online!`? Go to your server and type `!ping` 🎉 Type `!help` to see every command.

To stop the bot, click the terminal and press **Ctrl + C**. Always stop it before running it again!

## 🔒 The golden rule

Your token is your bot's password. Never paste it in Discord, in a screenshot, or on GitHub.
If it leaks: Developer Portal → Bot → **Reset Token**, then update `.env`.

## 🆘 Something broke?

| You see... | Fix |
|---|---|
| `PrivilegedIntentsRequired` | Part A step 3: turn on Message Content Intent and **Save**. |
| `LoginFailure: Improper token` | Re-copy your token into `.env`. No quotes, no spaces. Still broken? Reset Token. |
| Bot is online but ignores `!commands` | Message Content Intent is off, or you used `@bot.event` for `on_message`. Use `@bot.listen("on_message")`. |
| Bot replies **twice** | It's running in two terminals. Stop one with Ctrl + C (or the 🗑️ icon). |
| RPS buttons say "This interaction failed" | The game timed out (60 s) or your bot restarted. Start a new `!rps`. |
| New command missing from `!help` | You didn't restart the bot. Ctrl + C, then run it again. |
| `coroutine ... was never awaited` | You forgot `await` in front of something. |
| `IndentationError` | Line your code up with the lines around it (4 spaces per level). |
| `NameError` | Typo! Check spelling and capital letters. |

## ⭐ Fell behind?

Open `bot_complete.py`, copy the section you missed, and paste it into your `bot.py` **above** the `RUN THE BOT` part.

## 🏟️ Arena showdown

Post your bot's invite link (Part A step 4) in `#bot-invites`. Once the TA adds it, your commands work there instantly.

---

Built with [discord.py](https://github.com/Rapptz/discord.py) (MIT License).
This curriculum is free to reuse and adapt for your own school or club —
no permission needed, credit appreciated.

**Instructors:** [Jonathan Immanuel Montolalu](https://jomontolalu.com)
