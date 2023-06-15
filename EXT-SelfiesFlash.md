---
title: EXT-SelfiesFlash
description: 
published: true
date: 2023-03-28T14:56:35.520Z
tags: 
editor: markdown
dateCreated: 2022-11-23T18:19:21.303Z
---

> EXT-SelfiesFlash is a plugins for controling a flash light when you take a selfie with `EXT-Selfies`.
{.is-info}


> This module an Extented plugin of `EXT-Selfies`
> It can't work by itself without this plugin
{.is-danger}

> This module can display any errors with `EXT-Alert` plugin
{.is-warning}


# Installation
Clone the module into your MagicMirror module folder and execute `npm intall` in the modules directory.
```
cd ~/MagicMirror/modules
git clone https://github.com/bugsounet/EXT-SelfiesFlash
cd EXT-SelfiesFlash
npm install
```

# Configuration
> insert your configuration in the config.js file of MagicMirror.
{.is-info}

```js
{
  module: 'EXT-SelfiesFlash',
  config: {
    debug: false,
    gpio: 17
  }
},
```

> | Option  | Description | Type | Default |
> | ------- | --- | --- | --- |
> | debug | enable or not debug mode | Boolean | false |
> | gpio | BCM-number of the relay for controling the flash | Number | 17 |

# Usage
Just take a selfie and the flash light will turn on/off automaticaly

# Developer Notes

- This module will received this notification:
  * `EXT_SELFIESFLASH-ON` For turn on flash light
  * `EXT_SELFIESFLASH-OFF` For turn off flash light

# Update
> For updating this plugin try this command:
{.is-info}

```
cd ~/MagicMirror/modules/EXT-SelfiesFlash
npm run update
```

# Reinstall
> For reinstall this plugin, you can use this command:
{.is-info}

```
cd ~/MagicMirror/modules/EXT-SelfiesFlash
npm run rebuild
```

# Support and Helping
New forum and support for all @bugsounet modules is now localized [there](https://forum.bugsounet.fr) !