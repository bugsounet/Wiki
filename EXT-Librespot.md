---
title: EXT-Librespot
description: 
published: true
date: 2024-11-09T12:31:27.332Z
tags: 
editor: markdown
dateCreated: 2022-03-12T13:22:04.543Z
---

> This plugin is under recoding.
> v1.x don't work actually
> 
> --- Please wait EXT-Librespot v2.0.0 Release ---
{.is-danger}



EXT-Librespot

This plugin allow to play Spotify music on your mirror with Librespot

> This module is an Extented plugins for `EXT-Spotify`
{.is-info}

> In addition, you can use some plugins:
> `EXT-Alert` for display some information or error on your screen (Optional)
{.is-warning}


# Installation

Clone the module into your MagicMirror module folder and execute `npm intall` in the module's directory.
```
cd ~/MagicMirror/modules
git clone https://github.com/bugsounet/EXT-Librespot
cd EXT-Librespot
npm install
```

# Configuration
> To display the module insert it in the config.js file.
{.is-info}

```js
{
  module: 'EXT-Librespot',
  config: {
    debug: false,
    email: "",
    password: "",
    deviceName: "MagicMirror",
    minVolume: 40,
    maxVolume: 100
  }
},
```

|field  | description | type | default value
|---|---|---|---
|debug | Enable debug mode or not | BOOLEAN | false
|email | Your spotify email | STRING | null
|password | Your spotify password  | STRING | null
|deviceName | Define your spotify device name | STRING | MagicMirror
|minVolume | Min volume on Assistant activate | NUMBER | 40
|maxVolume | Max volume when spotify playing | NUMBER | 100

# Librespot player install
> To install Librespot player you have 2 choice:
{.is-info}

---
1) `npm run setup` command
> It will fetch `Librespot` player from `raspotify` preconfigured packet
> (very quick install!)
{.is-info}

```
cd ~/MagicMirror/modules/EXT-Librespot
npm run setup
```

---
2) `npm run setup:source` command
> If you prefer build `Librespot` player from github source
> (will take ~30 mins to install!)
{.is-info}

```
cd ~/MagicMirror/modules/EXT-Librespot
npm run setup:source
```
---
> For `EXT-Librespot` using, binary file of `Librespot` will be automaticaly added in `components/librespot` Folder
{.is-success}

# Logs of `Librespot` player
All logs of `Librespot` player is managed with `pm2` app
You can discover it with `pm2 log librespot` command for debuging (if needed)

# Update
```
cd ~/MagicMirror/modules/EXT-Librespot
npm run update
```
