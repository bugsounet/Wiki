---
title: EXT-Updates
description: 
published: true
date: 2024-12-31T01:10:34.775Z
tags: 
editor: markdown
dateCreated: 2023-07-08T16:40:04.617Z
---

The `updatenotification` module is one of the default modules of the MagicMirror.
This will display a message whenever a new version of the MagicMirror application is available.

Now, let's apply automatic updates on EXTs and MMM-GoogleAssistant
And restart MagicMirror when process is done (optional)

---
## Description

This module can **APPLY** any update of MMM-GoogleAssistant suite :)

> You can use [EXT-TelegramBot](/en/EXT-TelegramBot): for more control
{.is-warning}

# Installation & Configuration
1) [Installation](/en/EXT-Updates/Installation)
2) [Configuration](/en/EXT-Updates/Configuration)

# TelegramBot support (advised)
  * [Commands](/en/EXT-Updates/Commands)

# FULL response in natural languages
  * `en`, `fr`, `de`, `it`, `nl`, `es`
  * You can send me a new language file by translating default [english](https://github.com/bugsounet/EXT-Updates/blob/dev/translations/en.json) file to your own with `issue` or `pull request`

# Uninstall
```sh
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run remove:EXT-Updates
```

# Credits
 
  * Translaters:
    * Italian: @Saljoke
    * German: @lxne
    * French: @bugsounet
    * English: @bugsounet (with @sdetseil review)
    * Dutch: @Raf