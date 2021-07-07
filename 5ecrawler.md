---
title: 5eCrawler User Guide
description: 
published: true
date: 2021-07-07T22:32:40.823Z
tags: 
editor: markdown
dateCreated: 2021-07-07T22:32:40.823Z
---

# About 5eCrawler
5eCrawler is an in-development project, having forked from Avrae before D&D Beyond took over. It is part a suite of such tools DiscordCrawler, PokemonCrawler, or IssueCrawler.

All of these are Discord bots. If you are not familiar with Discord, it is, effectively a chat client with some voice and screen sharing services, and has rapidly become the most popular platform for Gaming, both for console gaming online and for Tabletop/Virtual tabletops. The bots work to automate and facilitate either Administration of a discord server (DiscordCrawler), manage content for game focus (5e = 5eCrawler; Pokenmon = PokemonCralwer), and group or project management - IssueCrawler (for managing support requests, features suggestions, Scheduling Groups and Event.)

# Getting Started
5eCrawler is a Discord bot designed to assist players and DMs by providing reference information via chat commands. To begin using the bot, simply invite the bot to join your server, configure it to your taste, and get to gaming!

So, for that let's directly link to where you likely want to go...

* [Invite it to your Discord server](https://discordapp.com/oauth2/authorize?client_id=559331529378103317&scope=bot&permissions=536977472)

## Inviting 5eCrawler to your server
You can easily invite the 5eCrawler bot to your own server by clicking [this link](https://discordapp.com/oauth2/authorize?client_id=559331529378103317&scope=bot&permissions=536977472%7Cthis)!

### 5eCrawler Discord Permissions
When invited, 5eCrawler will request five permissions which it will be assigned by default. Of the five permissions that it requests, four are optional and the last is mandatory for optimal usage of the bot.

If the mandatory permission is not allowed and one of the bot's commands are issued/requested, it will attempt to take the action and will leave the server if not able process the command. If added again and its needed rights are not provided, it will eventually block the server and you will not be able to add it again in the future. You have been warned.

**Mandatory:**

* Manage Messages - this allows the bot to remove messages from other users.

**Optional:**

* Manage Webhooks - there are two ways for the quote command to function: one where it will use a webhook to give a reply as the person who quoted the message, or one where it will just reply in text as the bot.

* Attach Files - some commands or replies will let the bot attach images/files and without this permission it will not be able to do so.

* Add Reactions - for the Anon/Delivery the bot requires to be able to add reactions to messages that are sent.

* Read History - for some things to work (Manage Messages, Add Reactions), the bot requires the ability to read the history of the channel. If it lacks this permission but has the "Add Reactions" permission, it will pelt you with a 'Permission not found.' message.

# Project History
The 5eCrawler is a separate project from 5eTools, and arose when [Avrae](https://avrae.io/)'s developer (Andrew Zhu), was hired to work with D&D Beyond. TheZhu did an INCREDIBLE job with his project.

The developer of 5eCrawler has removed some features (character sheets, play by post battle management) and reworked and rewritten the parser and dataset. Making 5eCrawler the most accurate means to look up 5e data within Discord, and has expanded its dataset to include many more categories to its lookup. It is also SRD-compliant.

# Code
Parts of the project's code are open source. Find them [here](https://github.com/CrawlerEmporium/).

# Content
The bot draws upon a number of resources, and RAW (Rules as Written / Official) SRD content is what it references. A intended patreon feature will be access to importable homebrews.

# Troubleshooting and Help
If you're having difficulty with 5eCrawler, see our [Troubleshooting and Support page for 5eCrawler](/help/5ecrawler).
You can use [crawleremporium.com](https://crawleremporium.com/bots/5ecrawler.php) for command reference.
If neither of the previous resources helped (or even if they did), join the [Crawler Emporium Discord server](https://discord.gg/HEY6BWj) to get help from other community members. 

# Support the Project
We appreciate any and all contributions to supporting 5eCrawler and the hardworking folks behind it. Here are a few ways you can contribute:
* [Support the project on Ko-fi](https://ko-fi.com/5ecrawler)
* [Support the author on Patreon](https://www.patreon.com/LordDusk)
* Submit a feature request or bug report on the [Cralwer Emporium Discord Server](https://discord.gg/HEY6BWj)