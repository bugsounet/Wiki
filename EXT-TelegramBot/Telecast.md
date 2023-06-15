---
title: Telecast
description: 
published: true
date: 2023-06-15T20:05:25.436Z
tags: 
editor: markdown
dateCreated: 2021-07-14T10:11:46.254Z
---

Since `v1.2.0`, You have `telecast` feature.

- send specific chat by command `/telecast` (See `Use commands`)
- telecasting chats from specific chat room(group) to MagicMirror without command. (See `Telecast chats`)

![](https://raw.githubusercontent.com/eouia/MMM-TelegramBot/master/sc_overflowed.png)

# telecast chats
- To enable telecasting chats from room(group) without command, you need 2 things before.
  1. Your telegramBot needs `privacy:disabled`. You can setup privacy mode of bot with `@botfather`.
  2. You should know `chatId` of target chat room and your bot is a member of that group. To get `chatId`, use `/mychatid` command in that room after inviting bot.
- Be careful to use. Bot could obtain private user information (name, profile photo, username and conversations), so you should know what you are doing. Explain to members and get consents before using. All rights and responsibilites are yours.
- All photos and text messages(except reply to bots) from human members will be telecasted.
- To use this feature, set `telecast: {chatId}`.
```js
telecast: "-1111111", // "-1111111" will be chatId of target room.
```

# Use commands
- Instead, a user can explicitly telecast his message with command `/telecast`. For example; `/telecast Kids! Time to go to bed!` will telecast the message "Kids! Time to go to bed".
```js
telecast: true,
```
- To send a photo, write caption with command `/telecast`.


# Not to use telecast
```js
telecast: null, // or `false`
```


# Looks
If you are using this on `*_bar`, `*_third`, `middle_center`, `telecastLimit:1` would be recommended.

You can override CSS in your `css/custom.css`