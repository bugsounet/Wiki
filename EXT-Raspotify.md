---
title: EXT-Raspotify
description: 
published: true
date: 2023-04-15T11:33:21.804Z
tags: 
editor: markdown
dateCreated: 2022-03-26T14:38:31.409Z
---

> This plugin will be deprecated soon!
> Please use `EXT-Librespot`
{.is-danger}

This plugin allow to play Spotify music on your mirror with Raspotify depenency

> This module is an Extented plugins for `EXT-Spotify`
{.is-info}

> In addition, you can use some plugins:
> `EXT-Alert` for display some information or error on your screen (Optional)
{.is-warning}


# Installation
Clone the module into your MagicMirror module folder and execute `npm install` in the module's directory.
```
cd ~/MagicMirror/modules
git clone https://github.com/bugsounet/EXT-Raspotify
cd EXT-Raspotify
npm install
```

# Configuration
> To display the module insert it in the config.js file.
{.is-info}

```js
{
  module: 'EXT-Raspotify',
  config: {
    debug: false,
    email: "",
    password: "",
    deviceName: "MagicMirror",
    deviceCard: "hw:CARD=Headphones,DEV=0",
    minVolume: 50,
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
|deviceCard | Define the playing device card | STRING | null
|minVolume | Volume to set when assistant speaking (in %) | NUMBER | 50
|maxVolume | Max volume when spotify playing (in %) | NUMBER | 100

# Raspotify service setup
> To setup the raspotify service follow this commands:
{.is-info}

> This command with read the module configuration and setup Raspotify service
{.is-warning}


```js
cd ~/MagicMirror/modules/EXT-Raspotify
npm run setup
```

# deviceCard

You can choose what device music Raspotify have to playing music

Generaly:

 * For Headphone (jack plug)
  `deviceCard: "hw:CARD=Headphones,DEV=0"`
 * For HDMI
  `deviceCard: "hw:CARD=b1,DEV=0"`

You can list all devices with `librespot --device ?` command

# WARN
> If you want to update your config and apply new setting
> Don't forget to run again:
{.is-warning}


```js
cd ~/MagicMirror/modules/EXT-Raspotify
npm run setup
```

# Update
> When a new version is available, update properly this plugin with:
{.is-success}

```
cd ~/MagicMirror/modules/EXT-Raspotify
npm run update
```

# Uninstall Raspotify
If you want to install `raspotify`

```
cd ~/MagicMirror/modules/EXT-Raspotify
npm run remove
```