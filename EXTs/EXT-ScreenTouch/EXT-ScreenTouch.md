---
title: EXT-ScreenTouch
description: 
published: true
date: 2023-03-28T15:00:58.723Z
tags: 
editor: markdown
dateCreated: 2022-03-13T10:18:18.123Z
---

EXT-ScreenTouch is a module for the [MagicMirror](https://github.com/MichMich/MagicMirror) project by [Michael Teeuw](https://github.com/MichMich).

> This plugins allow to turn on/off your screen with touch screen
{.is-info}

> This module is an Extented plugins for `MMM-GoogleAssistant`
{.is-info}

> This module a plugin for `EXT-Screen`, You need install it for using
> This plugin is not compatible with `EXT-ScreenManager`
{.is-danger}

# Installation
Clone the module into your MagicMirror module folder and execute `npm intall` in the module's directory.
```
cd ~/MagicMirror/modules
git clone https://github.com/bugsounet/EXT-ScreenTouch
cd EXT-ScreenTouch
npm install
```

# Configuration

> module to turn on/off your screen with touch screen
{.is-info}

## Sample
```js
{
  module: 'EXT-ScreenTouch',
  config: {
    mode: 3 
  }
},
```

## Details

> |field | description | type | default value
> |---|---|---|---
> | mode | selected mode for enable/disable the screen with touch | NUMBER | 3

 * Available mode:
   - `mode: 1`
     - One click on the screen will restart the timer (or Wake up the screen if needed)
     - Double Click on the screen will shutdown the screen
   - `mode: 2`
     - One Click on the EXT-Screen area will restart the timer
     - Long Click on the screen will shutdown or wake up the screen (toogle)
   - `mode: 3`
     - One Click on the EXT-Screen area will restart the timer
     - Doucle Click on the EXT-Screen area will shutdown the screen
     - One Click on the screen will wake up if shutdown


# Update
```sh
cd ~/MagicMirror/modules/EXT-ScreenTouch
npm run update
```