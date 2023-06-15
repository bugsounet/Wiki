---
title: EXT-YouTubeVLC
description: 
published: true
date: 2022-07-02T10:26:02.832Z
tags: 
editor: markdown
dateCreated: 2022-02-27T12:22:02.837Z
---

EXT-YouTubeVLC is a module for the [MagicMirror](https://github.com/MichMich/MagicMirror) project by [Michael Teeuw](https://github.com/MichMich).

It allow to display YouTube video in fullscreen on MagicMirror with VLC media player

> This module is an Extented for `MMM-GoogleAssistant` v4.x.
> You can naturally use it as a simple module !
> It can be controled with `MMM-TelegramBot` or with some notifications
{.is-info}


> This module need `EXT-Alert` plugins to display any errors and display current title playing
{.is-warning}


# Installation

Needed:
  * MagicMirror v2.18.0 and above
  * Node v16.x
  * npm v8.x

Clone the module into your MagicMirror module folder and execute `npm intall` in the module's directory.
```
cd ~/MagicMirror/modules
git clone https://github.com/bugsounet/EXT-YouTubeVLC
cd EXT-YouTubeVLC
npm install
```

# Configuration

> To display the module insert it in the config.js file.
{.is-info}

```js
{
  module: 'EXT-YouTubeVLC',
  config: {
    debug: false,
    useSearch: true,
    displayHeader: true,
    minVolume: 30,
    maxVolume: 100
  }
},
```

> | Option  | Description | Type | Default |
> | ------- | --- | --- | --- |
> | debug | enable or not debug mode | Boolean | false |
> | useSearch| activate YouTube search functionality (need `tokenYT.json` token and `credentials.json`) | Boolean | true
> | displayHeader | display a few seconds in popup the title found of the video (needed `EXT-Alert`) | Boolean | true 
> | minVolume | Volume to set when assistant speaking (in %) | Number | 30
> | maxVolume | Volume to set when video playing (in %) | Number | 100

# Google credentials (`credendials.json`)

The search functionality need google credentials file
You can create it with following this [wiki part](https://wiki.bugsounet.fr/en/MMM-GoogleAssistant/GoogleAssistantSetup).
Save the result file and rename it to `credentials.json` file into the root of this module (inside your EXT-YouTubeVLC folder)

> If you have already create it with `MMM-GoogleAssistant`, this module will search it automaticaly and use it.
> So it's not necessary to create it or past it
{.is-success}

# YouTube token for search functionality (`tokenYT.json`)

MMM-YouTube need an access to your youtube account for search functionality.
  * You have to activate the YouTube Data API v3
 [there](https://console.developers.google.com/apis/library/youtube.googleapis.com?q=youtube) [Not needed if already activated]
  * Generate the YouTube token for search functionality and voice control:
```
cd ~/MagicMirror/modules/EXT-YouTubeVLC
npm run token
```

# recipe for `MMM-GoogleAssistant` for vocal control
A prepared recipe is inclued and waiting for your use
Just add it in the config of MMM-GoogleAssistant

 * sample:
```js
recipes: [
  "../../EXT-YouTubeVLC/recipe/EXT-YouTubeVLC.js",
],
```
 * if you have other recipe, just add it like this:
```js
recipes: [
  "my_recipe.js",
  "../../EXT-YouTubeVLC/recipe/EXT-YouTubeVLC.js",
],
```

# `MMM-GoogleAssistant` Commands:
Activate your assistant with your prefered keyword and try:
 * `youtube <artist/Title>`: for search and display a video
   * Sample: `youtube Michael jackson thriller`
 * `stop`: will stop any video

# `MMM-TelegramBot` Commands:
You can control EXT-YouTubeVLC with TelegramBot
The main command is `/youtube`

 * **/youtube play \<Video ID>**: YouTube will playing your request of Video ID
 * **/youtube stop**: YouTube video ended.
 * **/youtube search \<title/artist>**: YouTube will search and play video of the search result

# Developer Notes
## Incoming notification:
 * `EXT_YOUTUBEVLC-PLAY <video ID>`: Start a wanted video ID
 * `EXT_YOUTUBEVLC-STOP`: Stop the video
 * `EXT_YOUTUBEVLC-SEARCH <Artist / Title>`: for search after a title artist video
 * `EXT_YOUTUBEVLC-VOLUME_MAX`: Set the volume to `maxVolume` from config
 * `EXT_YOUTUBEVLC-VOLUME_MIN`: Set the volume to `minVolume` from config

## Outgoing notification:
  * `EXT_YOUTUBEVLC-CONNECTED`: When video start
  * `EXT_YOUTUBEVLC-DISCONNECTED`:  When Video end

## When a video is playing:
> This module will hide all modules when a video is playing
> It's the better way to disable all modules to increase RPI performance
> It will use `EXT-YT_LOCKED` lockString
{.is-warning}

# Update
```
cd ~/MagicMirror/modules/EXT-YouTubeVLC
npm run update
```

