---
title: EXT-Librespot
description: 
published: true
date: 2024-12-31T00:59:07.796Z
tags: 
editor: markdown
dateCreated: 2022-03-12T13:22:04.543Z
---

EXT-Librespot

This plugin allow to play Spotify music on your mirror with Librespot

> This module is an Extented plugins for `EXT-Spotify`
{.is-info}

# Installation

Execute `npm run install:EXT-Librespot` in the MMM-GoogleAssistant's folder.
```
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run install:EXT-Librespot
```

# Configuration
> To display the module insert it in the config.js file.
{.is-info}

```js
{
  module: 'MMM-GoogleAssistant/EXTs/EXT-Librespot',
  config: {
    debug: false,
    deviceName: "MagicMirror",
    minVolume: 40,
    maxVolume: 100
  }
},
```

|field  | description | type | default value
|---|---|---|---
|debug | Enable debug mode or not | BOOLEAN | false
|deviceName | Define your spotify device name | STRING | MagicMirror
|minVolume | Min volume on Assistant activate | NUMBER | 40
|maxVolume | Max volume when spotify playing | NUMBER | 100

# Librespot player install

> build `Librespot` player from github source
> (will take ~30 mins to install!)
{.is-info}

```
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run setup:EXT-Librespot
```
---
> For `EXT-Librespot` using, binary file of `Librespot` will be automaticaly added in `EXTs/EXT-Librespot/components/librespot` Folder
{.is-success}

# Using
Open your spotify player (on your phone/computer/...)
Select `MagicMirror` (speaker) for music playing destination
MMM-GoogleAssistant will playing it and displaying any informations from `EXT-Librespot`

# Logs of `Librespot` player
All logs of `Librespot` player is managed with `pm2` app
You can discover it with `pm2 log librespot` command for debuging (if needed)

# Update
```
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run update
```

# Uninstall
```sh
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run remove:EXT-Librespot
```