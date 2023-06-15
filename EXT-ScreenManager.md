---
title: EXT-ScreenManager
description: 
published: true
date: 2023-06-15T20:02:58.368Z
tags: 
editor: markdown
dateCreated: 2022-03-05T17:35:32.992Z
---

EXT-ScreenManager is a module for the [MagicMirror](https://github.com/MichMich/MagicMirror) project by [Michael Teeuw](https://github.com/MichMich).

> This plugins will Automaticaly turn ON and Turn OFF your screen with defined hours
{.is-info}

> This module is an Extented plugins for `MMM-GoogleAssistant`
{.is-info}

> This module a plugin for `EXT-Screen`, You need install it for using
{.is-danger}

# Installation
Clone the module into your MagicMirror module folder and execute `npm intall` in the module's directory.
```
cd ~/MagicMirror/modules
git clone https://github.com/bugsounet/EXT-ScreenManager
cd EXT-ScreenManager
npm install
```

Automaticaly turn ON and Turn OFF your screen with defined hours

# Configuration Sample
> To use the module insert it in the config.js file.
{.is-warning}

```js
{
  module: 'EXT-ScreenManager',
  config: {
    debug: true,
    forceLock: true,
    ON: [
      "0 8 * * *"
    ],
    OFF: [
      "0 22 * * *"
    ]
  }
},
```

# Configuration Structure

> | Option  | Description | Type | Default |
> | ------- | --- | --- | ---
> | debug| Activate debug mode BOOLEAN| false
> | forceLock| Force to lock the screen counter and disable it | BOOLEAN | true
> | ON | Defined cron ON time | ARRAY of String | []
> | OFF | Defined cron OFF time | ARRAY of String | []

## `ON: []` and `OFF: []`

> This is the rule to Turn ON et Turn OFF your screen
> You have make to script your rule in cron format
> For each field, you can make an array of cron value
{.is-info}

In the sample Configuration,

I have set this rule for turn on screen:
```js
      ON: [
        "45 7 * * 0-4",
        "0 8 * * 5"
      ],
```
1st Rule: from Monday to Thursday at 07h45<br>
2nd Rule: every Friday at 08h00<br>

I have set this rule for turn off screen:
```js
      OFF: [
        "0 17 * * 0-5"
      ]
```
1st Rule: from Monday to Friday at 17h00

# Cron Syntax

This is a quick reference to cron syntax

## Allowed fields

```
 ┌────────────── second (optional)
 │ ┌──────────── minute
 │ │ ┌────────── hour
 │ │ │ ┌──────── day of month
 │ │ │ │ ┌────── month
 │ │ │ │ │ ┌──── day of week
 │ │ │ │ │ │
 │ │ │ │ │ │
 * * * * * *
```

## Allowed values

|     field    |        value        |
|--------------|---------------------|
|    second    |         0-59        |
|    minute    |         0-59        |
|     hour     |         0-23        |
| day of month |         1-31        |
|     month    |     1-12 (or names) |
|  day of week |     0-7 (or names, 0 or 7 are sunday)  |

# Notes
>   You can verify your cron value with [this site](https://crontab.guru/)
>   This plugin have no visual
{.is-warning}


# Update

  ```sh
  cd ~/MagicMirror/modules/EXT-ScreenManager
  npm run update
  ```
