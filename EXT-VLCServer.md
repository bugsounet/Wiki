---
title: EXT-VLCServer
description: 
published: true
date: 2024-12-31T01:11:11.103Z
tags: 
editor: markdown
dateCreated: 2024-05-04T11:33:21.021Z
---

This plugin play wanted media on `MagicMirror²` with `VLC`

![](https://raw.github.com/bugsounet/MMM-GoogleAssistant/dev/EXTs/EXT-VLCServer/vlc-logo.png)

> This plugin is an Extented plugins for:
>  `EXT-MusicPlayer`
>  `EXT-RadioPlayer`
>  `EXT-FreeboxTV`
{.is-info}

# Installation

Execute `npm run install:EXT-VLCServer` in the MMM-GoogleAssistant's folder.

```sh
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run install:EXT-VLCServer
```

# Configuration
> To display the module insert it in the config.js file.
{.is-info}

## Minimal configuration

```js
{
  module: 'MMM-GoogleAssistant/EXTs/EXT-VLCServer'
},
```

## Advanced Configuration

```js
{
  module: 'MMM-GoogleAssistant/EXTs/EXT-VLCServer',
  disabled: false,
  config: {
    debug: false,
    vlcPath: "/usr/bin"
  }
},
```

|field  | description | type | default value
|---|---|---|---
|debug | Enable debug mode or not | BOOLEAN | false
|vlcPath | Path of `vlc` app | STRING | "/usr/bin"

# Update

```sh
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run update
```

# Uninstall
```sh
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run remove:EXT-VLCServer
```

# Developer notifications

 * Send `EXT_VLCSERVER-START`: When server is started and ready for use
 * Send `EXT_VLCSERVER-CLOSE`: When server is close (can't be started or fatal error detected)
 
# VLC Server Specifications

 * This server use `http` protocol on `127.0.0.1` and `8082` port with `EXT-VLCServer` password