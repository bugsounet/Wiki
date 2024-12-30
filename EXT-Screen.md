---
title: EXT-Screen
description: 
published: true
date: 2024-12-30T16:32:54.283Z
tags: 
editor: markdown
dateCreated: 2022-02-25T00:04:52.369Z
---

After a configurated time without any user interaction the display will turn off and hide all modules for economy mode.

This module is an Extented plugins for `MMM-GoogleAssistant`

> In addition, you have use [MMM-Pir](https://github.com/bugsounet/MMM-Pir) modules to control it
{.is-warning}


# Installation

Execute `npm run install:EXT-Screen` in the MMM-GoogleAssistant's folder.
```sh
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run install:EXT-Screen
```

This module will verify if all screen saver is disabled and disable it if needed

# Configuration
> To display the module insert it in the config.js file.
>  This is the default configuration defined if you don't define any value.
{.is-info}

```js
{
  module: 'MMM-GoogleAssistant/EXTs/EXT-Screen',
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
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run update
```
