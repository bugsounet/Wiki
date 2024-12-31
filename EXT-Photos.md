---
title: EXT-Photos
description: 
published: true
date: 2024-12-31T01:02:42.804Z
tags: 
editor: markdown
dateCreated: 2022-02-28T21:28:29.045Z
---

EXT-Photos is a plugins for displaying any photos urls in full-screen discover by assistant 

# Installation

> Execute `npm run install:EXT-Photos` in the MMM-GoogleAssistant's folder.
{.is-info}

```sh
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run install:EXT-Photos
```

# Configuration

> Insert your configuration in the config.js file of MagicMirror.
{.is-info}

```js
{
  module: "MMM-GoogleAssistant/EXTs/EXT-Photos",
  config: {
    debug: false,
    displayDelay: 20 * 1000,
    loop: false
  }
},
```

> | Option  | Description | Type | Default |
> | ------- | --- | --- | --- |
> | debug | Enable or not debug mode | Boolean | false |
> | displayDelay| Delay before change photo automaticaly in ms. (default is 20 secs) | Number | 20000 |
> | loop | Make a loop on all photos | Boolean | false |

# MagicMirror  `electronOptions`

A new part of config is needed for displaying this module.

On the begining of MagicMirror config.js, modify with `electronOptions`

```js
var config = {
  address: "localhost",
  electronOptions: {
    webPreferences: {
      webviewTag: true
    }
  },
  port: 8080,
...
```

# Developer Notes
## Incoming notification:
 * `EXT_PHOTOS-OPEN`: 
   * Open the photo player with the URLs designed in `payload`.
   * `payload` must be an Array of URLs
 * `EXT_PHOTOS-CLOSE`: Close the photo player

## Outgoing notification:
  * `EXT_PHOTOS-CONNECTED`: When the photo player just open
  * `EXT_PHOTOS-DISCONNECTED`:  When the photo player just close

## When the photo player is open:
> This module will hide all modules for open the photo player
> It's the better way to disable all modules to increase RPI performance
> It will use `EXT_PHOTOS-LOCKED` lockString
{.is-warning}

# Update
```
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run update
```

# Uninstall
```sh
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run remove:EXT-Photos