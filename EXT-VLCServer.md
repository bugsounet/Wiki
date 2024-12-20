---
title: EXT-VLCServer
description: 
published: true
date: 2024-11-09T11:44:10.757Z
tags: 
editor: markdown
dateCreated: 2024-05-04T11:33:21.021Z
---

This plugin play wanted media on `MagicMirror²` with `VLC`

![](https://github.com/bugsounet/EXT-VLCServer/blob/dev/vlc-logo.png?raw=true)

> This plugin is an Extented plugins for:
>  `EXT-MusicPlayer`
>  `EXT-RadioPlayer`
>  `EXT-FreeboxTV`
{.is-info}

# Installation

Clone the module into your MagicMirror module folder and execute `npm intall` in the module's directory.

```sh
cd ~/MagicMirror/modules
git clone https://github.com/bugsounet/EXT-VLCServer
cd EXT-VLCServer
npm install
```

# Configuration
> To display the module insert it in the config.js file.
{.is-info}

## Minimal configuration

```js
{
  module: 'EXT-VLCServer'
},
```

## Advanced Configuration

```js
{
  module: 'EXT-VLCServer',
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
cd ~/MagicMirror/modules/EXT-VLCServer
npm run update
```

# Developer notifications

 * Send `EXT_VLCSERVER-START`: When server is started and ready for use
 * Send `EXT_VLCSERVER-CLOSE`: When server is close (can't be started or fatal error detected)
 
# VLC Server Specifications

 * This server use `http` protocol on `127.0.0.1` and `8082` port with `EXT-VLCServer` password