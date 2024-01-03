---
title: TelegranBot Commands
description: 
published: true
date: 2024-01-03T02:09:51.033Z
tags: 
editor: markdown
dateCreated: 2022-03-14T23:21:50.226Z
---

MMM-GoogleAssistant have some prepared commands for [`EXT-TelegramBot`](https://github.com/bugsounet/EXT-TelegramBot)

# query
 - description: activate assistant with your text query
 - arguments: your query
 - exemples:
```
/query <question>
```

# stop
 - description: Stop Extented plugins process if running (radio, youtube, links, photos or cast)
 - arguments: none
 - exemple:
```
/stop
```

# sysinfo
 - description: show system informations of your system
 - arguments: none | show | hide
 - exemples:
```
/sysinfo: Sends a summary of the state of your system in Telegram
/sysinfo show: Will display state of your system in MagicMirror
/sysinfo hide: Will close sysinfo windows of MagicMirror
```