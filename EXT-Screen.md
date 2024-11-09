---
title: EXT-Screen
description: 
published: true
date: 2024-11-09T11:50:46.378Z
tags: 
editor: markdown
dateCreated: 2022-02-25T00:04:52.369Z
---

After a configurated time without any user interaction the display will turn off and hide all modules for economy mode.

This module is an Extented plugins for `MMM-GoogleAssistant`

> In addition, you have use [MMM-Pir](https://github.com/bugsounet/MMM-Pir) modules to control it
{.is-warning}


# Installation

Clone the module into your MagicMirror module folder and execute `npm intall` in the module's directory.
```
cd ~/MagicMirror/modules
git clone https://github.com/bugsounet/EXT-Screen
cd EXT-Screen
npm install
```

This module will verify if all screen saver is disabled and disable it if needed

# Configuration
> To display the module insert it in the config.js file.
{.is-info}


## Minimal configuration
```js
{
  module: 'EXT-Screen',
  config: {
    detectorSleeping: false
  }
},
```
## Personalized configuration
>  This is the default configuration defined if you don't define any value.
>  Don't copy/past the entire default config, just add in default config your needed new change value !
>  all new value will automaticaly be merged with the default config
{.is-info}


```js
{
  module: 'EXT-Screen',
  config: {
    debug: false,
    detectorSleeping: false
  }
},
```

## Detailed Configuration

> | Option  | Description | Type | Default |
> | ------- | --- | --- | --- |
> | debug | Enable debug mode | Boolean | false |
> | detectorSleeping | Activate EXT-Detector only when display is on | Boolean | false |

## Update
```sh
cd ~/MagicMirror/modules/EXT-Screen
npm run update
```
