---
title: EXT-UpdateNotification
description: 
published: true
date: 2023-06-15T20:06:18.263Z
tags: 
editor: markdown
dateCreated: 2022-03-05T17:31:20.395Z
---

The `updatenotification` module is one of the default modules of the MagicMirror.<br>
This will display a message whenever a new version of the MagicMirror application is available.

---
This module is a Fork of `Update Notication` default module of MagicMirror and recoded for better use

* Added: TelegramBot notification and functions
* Added: Auto-Updater my own mpn libraries
* Added: Auto-updater any `EXTs plugins`, `MMM-GoogleAssistant` and `Gateway`
* Denied: Auto-update `MagicMirror` and others `MMM modules`
* Added: Auto-restart your mirror (`pm2` app version or `npm start` version)

## Description

This module can **FIND** and **APPLY** any update of your modules :)

Because in **UpdateNotification** there is 2 words !

 * **Notification:**
   * Display notifications on your screen
   * Display notifications on Telegram via [TelegramBot](https://wiki.bugsounet.fr/EXT-TelegramBot)
 * **Update:**
   * Find any available module updates
   * Self apply any authorized update
   * Display update process via telegramBot (callback), terminal or log file
   * If not telegramBot used, Display update process with `EXT-Alert` module
   * Auto Restart MagicMirror when update is done !

> **WARNING**: This module will make you lazy !
{.is-warning}

> This module need [EXT-Alert](/en/EXT-Alert), if you don't use [EXT-TelegramBot](/en/EXT-TelegramBot)
{.is-warning}

# Installation & Configuration
1) [Installation](/en/EXT-UpdateNotification/Installation)
2) [Configuration](/en/EXT-UpdateNotification/Configuration)

> **If you use this module:** You can delete or disable the default `updatenotification` module
> otherwise, you will have double notification !
{.is-danger}

# TelegramBot support (advised)
  * [Commands](/en/EXT-UpdateNotification/Commands)

# FULL response in natural languages
  * `en`, `fr`, `de`, `it`, `nl`
  * You can send me a new language file by translating default [english](https://github.com/bugsounet/EXT-UpdateNotification/blob/dev/translations/en.json) file to your own with `issue` or `pull request`

# Credits

  * Programmer:
    - @MichMich (original updatenotification)
    - @bugsounet
    
  * Translaters:
    * Italian: @Saljoke
    * German: @lxne
    * French: @bugsounet
    * English: @bugsounet (with @sdetseil review)
    * Dutch: @Raf
 