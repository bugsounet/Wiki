---
title: EXT-Pir
description: 
published: true
date: 2024-09-13T09:30:47.152Z
tags: 
editor: markdown
dateCreated: 2022-02-26T21:02:26.205Z
---

> EXT-Pir is a plugins for control your screen with a PIR Sensor.
{.is-info}

> This module an Extented plugin of `EXT-Screen`
> It can't work by itself without this plugin
{.is-danger}

> This module can display any errors with `EXT-Alert` plugin
{.is-warning}

# Installation

Clone the module into your MagicMirror module folder and execute `npm run setup` in the modules directory.
```
cd ~/MagicMirror/modules
git clone https://github.com/bugsounet/EXT-Pir
cd EXT-Pir
npm run setup
```

# Configuration
> insert your configuration in the config.js file of MagicMirror.
{.is-info}


```js
{
  module: 'EXT-Pir',
  config: {
    debug: false,
    gpio: 21,
    mode: 0
  }
},
```

> | Option  | Description | Type | Default |
> | ------- | --- | --- | --- |
> | debug | enable or not debug mode | Boolean | false |
> | gpio | BCM-number of the sensor pin | Number | 21 |
> | mode | Detection mode (see bellow) | Number | 0 |

* Available mode:
   - `mode: 0` - use `node-libgpiod` library
   - `mode: 1` - use python script with `gpiozero` library

* `gpio` value:
  - Consult gpio doc at https://pinout.xyz/ 

# Developer Notes

- This module broadcasts:
  * `EXT_SCREEN-WAKEUP` notification for wake up your screen

# Update
> For updating this plugin try this command:
{.is-info}

```
cd ~/MagicMirror/modules/EXT-Pir
npm run update
```

# Reinstall
> For reinstall this module or when an update of MagicMirror² is available, you can use this command:
{.is-info}
```
cd ~/MagicMirror/modules/EXT-Pir
npm run rebuild
```

# Support and Helping
🛠️ For personalized assistance, visit https://www.bugsounet.fr and create a ticket