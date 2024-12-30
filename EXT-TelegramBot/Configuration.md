---
title: Configuration
description: 
published: true
date: 2024-12-30T16:56:10.154Z
tags: 
editor: markdown
dateCreated: 2021-07-14T09:41:26.991Z
---

# Configuration option

> use config.js file of MagicMirror for configuring EXT-TelegramBot
{.is-warning}


```js
{
  module: 'MMM-GoogleAssistant/EXTs/EXT-TelegramBot',
  position: "top_left",
  config: {
    debug: false,
    telegramAPIKey : '<your Telegram API Token>',
    allowedUser : ['<your Telegram username without @>'],
    adminChatId : <your admin chat id>,
    useWelcomeMessage: false,
    favourites:["/commands", "/modules", "/hideall", "/showall"],
    detailOption: {},
    telecast: null, // true or chat_id
    telecastLife: 1000 * 60 * 60 * 6,
    telecastLimit: 5,
    telecastHideOverflow: true,
    commandAllowed: {},
    useSoundNotification: true,
    dateFormat: "DD-MM-YYYY HH:mm:ss",
    telecastContainer: 300,
    screenshotTool: "grim"
  }
},
```

**`debug`** : If set as `false`, log will not be logged.

**`useWelcomeMessage`** : if set as `false`, Wake-up message will not happen.

**`favourites`** : put your favourite commands to telegram keyboard. They will be loaded by command `/favor`

**`detailOption`** : For Developer/Expert. Set detail options for `note-telegram-bot-api` constructor (https://github.com/yagop/node-telegram-bot-api/blob/5169d79bd92495d169f9e49302b9f5c630c6ccfc/src/telegram.js#L186)

**`telecast`** : `null` for disallowance. `true` for activating by only `/telecast` command. `"{chatId}"` for telecasting whole chats in specific chat room. (Read the wiki)

**`telecastLife`** : ms of lifetime of chat. After this time, chat will be disappeared and cache data also be removed.

**`telecastLimit`** : How many chats be displayed. Older chat will be shifted by new one.

**`telecastHideOverflow`** : on `true`, when overflowed old chats will be hidden. (defined by CSS) If you have touch/mouse interface, you can scroll hidden area.
> Telecast might have different look by position of module. on .bar, .middle.center, .third region, `telecastLimit:1` would be better. Or modify CSS by yourself.

**`commandAllowed`** : command would be executable by only specific users. Others, even in `allowedUser` cannot use it.

In this example:
   - `me` and `john` can execute **`/telecast`** command, but `jane` cannot.
   - only `me` can execute **`/mychatid`** command. The others can't.
   - `jane` can execute all other commands except **`/telecast`** and **`/mychatid`**.
   - `"modules":[],` will be ignored. It does not mean "Nobody can use this command.
```js
allowedUser: ["me", "john", "jane"],
commandAllowed: {
  "telecast": ["me", "john"],
  "mychatid": ["me"],
  "modules": [],
}
```

**`useSoundNotification`** : Use Official notification sound, on incomming messages

**`dateFormat`** : Your prefered date format

**`telecastContainer`**: force le with of the telecast container in px. Default: 300, mini: 200, max : 1000

**`screenshotTool`**: Set screenshot tool to use for `/screenshot` command
- `grim`: This tool is designed for Wayland or LabWc compositor using (default)
- `scrot`: This tool is designed for X11 compositor using