---
title: What is available with TelegramBot
description: 
published: true
date: 2023-08-05T09:42:01.832Z
tags: 
editor: markdown
dateCreated: 2021-07-14T10:25:34.687Z
---

A common `MagicMirror` might have limited interfaces for user input and output. `TelegramBot` could add an extended interface to your module.

These are just suggestions which your module could be extended.

## Instant report
Your module can send a report to admin directly even if he is not seeing `MagicMirror` or he is not in the same space.

Suppose your module is monitoring the temperature of a room. Currently, your module is just displaying the temperature on the mirror. But with `TelegramBot`, your module could send the temperature information to admin's cell phone directly.

## User input
Some mirrors might have a touchscreen, some might have voice commander and some might have a few buttons and sensors. But most of the mirrors don't have any input peripheral. With `TelegramBot`, your module can get the input from the user in various context.

Suppose your module has the ability to show game schedules of Football teams. A user can select his favorite team in `config.js` then your module will show the schedules of that team. However, your module could do more!
By lack of input interface, your module should have limitation for changing views. A dedicated button for the football team schedule changing? It's out of sense. Maybe touchscreen or voice commander could be a solution. But most of us have not.

With `TelegramBot`, your module can directly get user command for changing team with ease. Your module doesn't need dependency of `notification` from the anonymous input method modules.

## Rich response
Mirrors have also limited output. Usually, only mirror screen is that. Your module should compete against other modules for restricted real estates of screen size.

Suppose your football team schedule module again. Your module might be able to gather and have various information about football games already - regular starters, stadium location, scores, highlight clips and etc... But there is no space for those!

With `TelegramBot`, your module could reply more detailed information. A user can ask your module about many things. Your module could answer with not only text but also web-link, images, video clips, audio clips, files, map, contacts. Your module can tell the user about the ticket purchasing link and map of stadium!

## Remotely using
Even if he is working at his office, he can control his mirror in his room. All of these assumptions are available without any additional setting. The mirror doesn't need `Static IP`, `public domain` or `port forwarding`, or any other `something like clouds`. 

How do you think about these?