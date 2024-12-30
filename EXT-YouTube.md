---
title: EXT-YouTube
description: 
published: true
date: 2024-12-30T11:52:02.049Z
tags: 
editor: markdown
dateCreated: 2022-02-27T15:21:18.007Z
---

# Screenshoot:
YouTube windows in rest
![](https://raw.githubusercontent.com/bugsounet/MMM-GoogleAssistant/dev/EXTs/EXT-YouTube/resources/Screenshot1.png)

Youtube windows playing sample
![](https://raw.githubusercontent.com/bugsounet/MMM-GoogleAssistant/dev/EXTs/EXT-YouTube/resources/Screenshot2.png)

# Require:
>This plugin is Reserved to **Donators @bugsounet's website**
{.is-danger}

>There is some FreeDays for testing this module
>FreeDays days is defined every month from 01 to 07
>In other case/day, you can't use this module
{.is-info}

# Installing:

> This plugin is coded for working with `MMM-GoogleAssistant`
> For using with EXT-TelegramBot
> For using with notifications with somes modules
{.is-success}

Execute `npm run install:EXT-YouTube` in the MMM-GoogleAssisant Folder.

```sh
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run install:EXT-YouTube
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
  module: "MMM-GoogleAssistant/EXTs/EXT-YouTube",
  position: "top_center", // optional (can be deleted if using fullscreen)
  config: {
    fullscreen: false,
    width: "30vw",
    height: "30vh",
    useSearch: true,
    alwaysDisplayed: true,
    displayHeader: true,
    username: null,
    password: null
  }
},
```

# Detailed configuration:

>|Field|Type|Default|Description|
>|---|---|---|---|
>|fullscreen | boolean | false | enable fullscreen video (default in windows)|
>|width| string | 30vw | width of the your YouTube window (can be a px value too)
>|height| string | 30vh | heigth of the your YouTube window (can be a px value too)
>|useSearch| boolean | true | activate YT search functionality (need YT.json token)
>|alwaysDisplayed| boolean | true | should the YouTube windows have to be always displayed when a video is not playing ?
>|displayHeader| boolean | true | display name of the video in header
>|username| string | null | username of the @bugsounet's support forum
>|password| string | null | The password sended by @bugsounet (It's not your password of the forum !)

# recipe for `MMM-GoogleAssistant` for vocal control
A prepared recipe is inclued and waiting for your use
Just add it in the config of MMM-GoogleAssistant

 * sample:
```js
recipes: [
  "../../EXT-YouTube/recipe/EXT-YouTube.js",
],
```
 * if you have other recipe, just add it like this:
```js
recipes: [
  "my_recipe.js",
  "../../EXT-YouTube/recipe/EXT-YouTube.js",
],
```

# `MMM-GoogleAssistant` Commands:
Activate your assistant with your prefered keyword and try:
 * `youtube <artist/Title>`: for search and display a video
   * Sample: `youtube Michael jackson thriller`
 * `stop`: will stop any video

# `EXT-TelegramBot` Commands:
You can control MMM-Youtube with TelegramBot
The main command is `/youtube`

 * **/youtube play \<Video ID>**: YouTube will playing your request of Video ID
 * **/youtube stop**: YouTube video ended.
 * **/youtube search \<title/artist>**: YouTube will search and play video of the search result
{.is-info}

# Developer Notes
## Incoming notification:
 * `EXT_YOUTUBE-PLAY <video ID>`: Start a wanted video ID
 * `EXT_YOUTUBE-STOP`: Stop the video
 * `EXT_YOUTUBE-SEARCH <Artist / Title>`: for search after a title artist video
 * `EXT_YOUTUBE-VOLUME_MIN`: set the volume to 10% of the YouTube Player
 * `EXT_YOUTUBE-VOLUME_MAX`: set the volume to 100% of the YouTube Player

## Outgoing notification:
  * `EXT_YOUTUBE-CONNECTED`: When video start
  * `EXT_YOUTUBE-DISCONNECTED`:  When Video end

## When a video is playing:
> This module will hide all modules when a video is playing in fullscreen
> It's the better way to disable all modules to increase RPI performance
> It will use `EXT-YT_LOCKED` lockString
> When you call assistant, Volume Control increase/decrease volume automatically 
{.is-warning}


# FreeDays
>For displaying Video, this plugin use some resource on @bugsounet's server
>That's why i limit traffic for this module
>This module is limited to **Donators/Helpers/BetaTester Groups**
>But there is some FreeDays for testing this module
>FreeDays days is defined every month from 01 to 07
>
>In others days you need `credentials`(username and password) sended by @bugsounet 
>If you are in a needed group, just ask me to generate your `password` and place it in config field
>
> **Volume Control is not available, if you don't have credentials**
{.is-danger}

# Update
```
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run update
```