---
title: EXT-Motion
description: 
published: true
date: 2023-12-03T11:33:07.144Z
tags: 
editor: markdown
dateCreated: 2022-11-21T20:14:18.758Z
---

> EXT-Motion is a plugin for control your screen with a webcam as a motion detector.
{.is-info}


> This plugin an Extented plugin of `EXT-Screen`
> It can't work by itself without this plugin
{.is-danger}

> This plugin can display any errors with `EXT-Alert` plugin
{.is-warning}


# Installation

Clone the module into your MagicMirror module folder and execute `npm intall` in the modules directory.
```
cd ~/MagicMirror/modules
git clone https://github.com/bugsounet/EXT-Motion
cd EXT-Motion
npm install
```

# Configuration
> insert your configuration in the config.js file of MagicMirror.
{.is-info}


```js
{
  module: 'EXT-Motion',
  config: {
    debug: false,
    captureIntervalTime: 1000,
    scoreThreshold: 100,
    deviceId: null
  }
},
```

> | Option  | Description | Type | Default |
> | ------- | --- | --- | --- |
> | debug | enable or not debug mode | Boolean | false |
> | captureIntervalTime | Time in ms between capturing images for detection | Number | 1000 |
> | scoreThreshold | Threshold minimum for an image to be considered significant | Number | 100 |
> | deviceId | Specify which camera to use in case multiple exist in the system. (optional) | String | null |

# deviceId Feature
> In 99% of time you don't have to change `null` value of this feature (I consider that you have only one webcam plugged in your pi !)
{.is-success}

in other case, if you have SooOOoo many webcam, open the developer console (`npm start dev`) and try:
`navigator.mediaDevices.enumerateDevices()` to get all devices
and copy and past the `deviceId` of your needed device

# Developer Notes

- This module broadcasts:
  * `EXT_SCREEN-WAKEUP` notification for wake up your screen

# Update
> For updating this plugin try this command:
{.is-info}

```
cd ~/MagicMirror/modules/EXT-Motion
npm run update
```
