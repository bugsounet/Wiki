---
title: EXT-TelegramBot
description: 
published: true
date: 2024-12-31T01:08:46.892Z
tags: 
editor: markdown
dateCreated: 2021-07-10T19:23:10.867Z
---

TelegramBot plugin for MMM-GoogleAssistant<br>

> You can remote-control plugins within `Telegram`.
> The Bot is implemented in this plugin thus you don't need to manage antoher daemon.
> Other module developers can add their commands easily.
{.is-info}

> This module an Extented plugin of `MMM-GoogleAssistant`
> It can't work by itself without this !
> This plugin is dedicated to work with all plugins only !
{.is-danger}

# Screenshot

![](https://raw.githubusercontent.com/bugsounet/MMM-GoogleAssistant/dev/EXTs/EXT-TelegramBot/screenshot/sc_fullsize.png)

![](https://raw.githubusercontent.com/bugsounet/MMM-GoogleAssistant/dev/EXTs/EXT-TelegramBot/screenshot/sc_overflowed.png)

# Guide, installation, updating

 * [Installation](/en/EXT-TelegramBot/Installation)

 * [Configuration](/en/EXT-TelegramBot/Configuration)
 
 * [Commands List](/en/EXT-TelegramBot/CommandsList)
 
 * [Telecast](/en/EXT-TelegramBot/Telecast)

 * Update command:

```sh
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run update
```

  * Uninstall command:

```sh
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run remove:EXT-TelegramBot
```

# Developer tools

 * [How to add commands](/en/EXT-TelegramBot/DevCommands)
 * [What is available with TelegramBot](/en/EXT-TelegramBot/devAvailable)
 * [Guide for design command](/en/EXT-TelegramBot/devDesign)
 
 Coded by @eouia (MMM-TelegramBot main code) and @bugsounet (recoded, add new features, correct all bugs, optimization)