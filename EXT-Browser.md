---
title: EXT-Browser
description: 
published: true
date: 2022-03-13T12:11:55.439Z
tags: 
editor: markdown
dateCreated: 2022-02-28T20:52:02.081Z
---

EXT-Browser is a plugins for displaying any internet web page like a real browser in fullscreen

> This module need `EXT-Alert` plugins to display any errors or informations on the screen
{.is-warning}

# Installation

> Clone the module into your MagicMirror module folder and execute npm intall in the module's directory.
{.is-info}


```sh
cd ~/MagicMirror/modules
git clone https://github.com/bugsounet/EXT-Browser
cd EXT-Browser
npm install
```

# Configuration

> Insert your configuration in the config.js file of MagicMirror.
{.is-info}

```js
{
  module: "EXT-Browser",
  config: {
    debug: false,
    displayDelay: 60 * 1000,
    scrollActivate: false,
    scrollStep: 25,
    scrollInterval: 1000,
    scrollStart: 5000
  }
},
```

> | Option  | Description | Type | Default |
> | ------- | --- | --- | --- |
> | debug | Enable or not debug mode | Boolean | false |
> | displayDelay| Delay before closing the browser automaticaly in ms. If you want to disable this delay, set it to 0 (default is 60 secs) | Number | 60000 |
> | scrollActivate | Activate or not auto-scrolling | Boolean | false |
> | scrollStep | Scrolling step in px for scrolling down| Number | 25 |
> | scrollInterval | Scrolling interval for next scrollStep | Number | 1000 |
> | scrollStart | Delay before scrolling down in ms (after url loaded ) | Number | 5000 |

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
 * `EXT_BROWSER-OPEN`: Open the browser with the URL designed in `payload`
 * `EXT_BROWSER-CLOSE`: Close the browser

## Outgoing notification:
  * `EXT_BROWSER-CONNECTED`: When the browser just open
  * `EXT_BROWSER-DISCONNECTED`:  When the browser just close

## When the browser is open:
> This module will hide all modules for open the browser
> It's the better way to disable all modules to increase RPI performance
> It will use `EXT_LOCKED` lockString
{.is-warning}

# Update
```
cd ~/MagicMirror/modules/EXT-browser
npm run update
```