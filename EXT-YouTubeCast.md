---
title: EXT-YouTubeCast
description: 
published: true
date: 2024-11-09T11:39:36.935Z
tags: 
editor: markdown
dateCreated: 2022-02-27T17:29:54.360Z
---

It allow to cast a YouTube video on MagicMirror

> This module is an Extented for `MMM-GoogleAssistant`
{.is-info}

# Screenshoot

![](https://raw.githubusercontent.com/bugsounet/EXT-YouTubeCast/dev/resources/Screenshot1.png)
![](https://raw.githubusercontent.com/bugsounet/EXT-YouTubeCast/dev/resources/Screenshot2.png)

# Installing
Clone the module into your MagicMirror module folder and execute `npm intall` in the module's directory.
```
cd ~/MagicMirror/modules
git clone https://github.com/bugsounet/EXT-YouTubeCast
cd EXT-YouTubeCast
npm install
```

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

# Configuration

```js
{
  module: "EXT-YouTubeCast",
  position: "top_center", // optional (can be deleted if using fullscreen)
  config: {
    debug: false,
    fullscreen: false,
    width: "30vw",
    height: "30vh",
    alwaysDisplayed: true,
    castName: "MagicMirror",
    port: 8569
  }
},
```

# Detailed configuration

>|Field|Type|Default|Description|
>|---|---|---|---|
>|debug | boolean| false | enable or not debug mode |
>|fullscreen | boolean | false | enable fullscreen video (default in windows)|
>|width| string | 30vw | width of the your YouTube window (can be a px value too)
>|height| string | 30vh | heigth of the your YouTube window (can be a px value too)
>|alwaysDisplayed| boolean | true | should the YouTubeCast windows have to be always displayed when a video is not playing ?|
>|castName| string | MagicMirror | name of the cast device|
>|port| number | 8569 | port of the device|

# Using

Just open YouTube (or YouTube Music) app on your phone/tablet or with the youtube website in a computer
Click on the cast icon and select your device name defined in module configuration
The video will be played on your mirror !

> All devices must be in the same network
{.is-info}

# Developer Notes
## Incoming notification:
 * `EXT_YOUTUBECAST-STOP`: Stop the video

## Outgoing notification:
  * `EXT_YOUTUBECAST-CONNECTED`: When video start
  * `EXT_YOUTUBECAST-DISCONNECTED`:  When Video end

## When a video is playing:
> This module will hide all modules when a video is playing in fullscreen
> It's the better way to disable all modules to increase RPI performance
> It will use `EXT_LOCKED` lockString
{.is-warning}

# Update
```
cd ~/MagicMirror/modules/EXT-YouTubeCast
npm run update
```