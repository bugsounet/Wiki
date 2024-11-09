---
title: Configuration
description: 
published: true
date: 2024-11-09T10:48:37.010Z
tags: 
editor: markdown
dateCreated: 2023-07-08T17:07:02.669Z
---

# `updatenotification` configuration
`EXT-Updates` need `updatenotification` default module for working

Let's turn on feature for broacast any updates found!

Edit MagicMirror `config.js` file and modify `updatenotification` module configuration

```js
{
	module: "updatenotification",
	position: "top_bar",
	config: {
	  sendUpdatesNotifications: true
	}
},
```

# `EXT-Updates` configuration
use MagicMirror's `config.js` file to configure EXT-Updates

## Simple
```js
{
  module: "EXT-Updates",
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
  module: "EXT-Updates",
  config: {
    debug: false,
    autoUpdate: true,
    autoRestart: true,
    logToConsole: true,
    timeout: 2*60*1000,
    welcome: true
  }
},
```

# Configurable fields

|field | description | type | default value
|---|---|---|---
|debug | When you set `debug` to `true`, detailed log will be recorded. If you don't want log, set it to `false`. | BOOLEAN | false
|autoUpdate | If you want an automated update process, just activate it! | BOOLEAN | true
|autoRestart | Restart MagicMirror after update automatically. | BOOLEAN | true
|logToConsole | This feature is needed for user who don't use PM2 ! Log process and result in console| BOOLEAN | true
|timeout | maximum execution time of an update in ms | NUMBER | 2 * 60 * 1000
|welcome | Informs MagicMirror² PID process number at startup | BOOLEAN | true |

# Notes:
> If you use `pm2` app: `EXT-Updates` will detect it automaticaly!
{.is-info}
