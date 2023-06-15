---
title: Configuration
description: 
published: true
date: 2023-06-15T20:06:07.727Z
tags: 
editor: markdown
dateCreated: 2022-03-08T21:18:17.161Z
---

use MagicMirror's `config.js` file to configure EXT-UpdateNotification
# Simple
```js
{
  module: "EXT-UpdateNotification",
  position: "top_bar",
  configDeepMerge: true
},
```

# Full & Detailed

This is the default configuration if no values are defined

> This configuration is the same like sample !
> Don't copy and past it, if you don't modify it !
{.is-warning}


```js
{
  module: "EXT-UpdateNotification",
  position: "top_bar",
  configDeepMerge: true,
  config: {
    debug: false,
    updateInterval: 10 * 60 * 1000, // every 10 minutes
    startDelay: 60 * 1000, // delay before 1st scan
    ignoreModules: [],
    notification: {
      useTelegramBot: true,
      sendReady: true,
      useScreen: true,
      useCallback: true
    },
    update: {
      autoUpdate: true,
      autoRestart: true,
      usePM2: false,
      PM2Name: "0",
      logToConsole: true,
      timeout: 2*60*1000
    }
  }
},
```

> Don't forget to disable or delete default `updatenotification` module, otherwise you'll have duplicate notifications!
{.is-danger}


# Configurable fields
> You don't need to define all values of EXT-UpdateNotification config in `config.js` file
> If not set the default values are being used.
> Just pick what you need to override defaults.
{.is-success}


## Field in root of config

|field | description | type | default value
|---|---|---|---
|debug | When you set `debug` to `true`, detailed log will be recorded. If you don't want log, set it to `false`. | BOOLEAN | false
|updateInterval | Interval for update checking in ms. (default: 10 mins) | NUMBER | 10 * 60 * 1000
|startDelay | Sometimes, loading MagicMirror can be a real horse race... and the result of the first update check can be no value (ping timeout).<br> To prevent this set a delay before starting first scan (default : 60 secs) | NUMBER | 60 * 1000
|ignoreModules| Array of ignored modules | Array of String | []
|updateCommands| You can define individual update commands for each module with an array | Array of object | []

<br>

### Field `ignoreModules: []`

Array of ignored modules

sample:
```js
ignoreModules: ["MMM-Onemodule", "MMM-othermoduletodisable"]
```

### Field `notification: {}`

|field (- subFiled) | description | type | default value
|---|---|---|---
|notification |  | OBJECT | |
|- useTelegram | Do you use MMM-TelegramBot? | BOOLEAN | true |
|- sendReady| Send a welcome and initialized confirmation on start | BOOLEAN | true |
|- useScreen | Display update on the screen? | BOOLEAN | true |
|- useCallback | Send any callback process to telegramBot? | BOOLEAN | true|

<br>

### Field `update: {}`

|field (- subFiled) | desscription | type | default value
|---|---|---|---
|update |  | OBJECT | |
|- autoUpdate | If you want an automated update process, just activate it! | BOOLEAN | true
|- autoRestart | Restart MagicMirror after update automatically. | BOOLEAN | true
|- usePM2 | If you use PM2, activate it. | BOOLEAN | true
|- PM2Name | Name or ID of the MagicMirror process in PM2 | STRING | 0
|- logToConsole | This feature is needed for user who don't use PM2 ! Log process and result in console| BOOLEAN | true
|- timeout | maximum execution time of an update in ms | NUMBER | 2 * 60 * 1000

- autoUpdate: If you want an automated update process, just activate it!
- autoRestart: Restart MagicMirror after update automatically.
- usePM2: If you use PM2, activate it.
- PM2Name: Name or ID of the MagicMirror process in PM2
- updateMagicMirror: apply automaticaly any update of MagicMirror application
- logToConsole: This feature is needed for user who don't use PM2 !<br>
More informations in [[logToConsole]]
- timeout: maximum execution time of an update in ms

# Notes:
> If you use `npm start` for starting `MagicMirror`
> set `usePM2: false,` and `EXT-UpdateNotification` will be able to restart correctly your mirror
{.is-warning}

>  Don't forget to disable or delete default `updatenotification` module, otherwise you'll have duplicate notifications!
{.is-danger}

