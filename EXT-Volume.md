---
title: EXT-Volume
description: 
published: true
date: 2024-11-09T11:41:03.542Z
tags: 
editor: markdown
dateCreated: 2022-02-27T18:51:30.731Z
---

EXT-Volume is a plugins for controling the sound volume level of your mirror

> This module is an plugin for `MMM-GoogleAssistant`
> You can naturally use it as a simple module !
> It can be controled with `EXT-TelegramBot` or with some notifications
{.is-info}

## Screenshot
![](https://raw.githubusercontent.com/bugsounet/EXT-Volume/dev/resources/screenshot.png)

# Installation

Clone the module into your MagicMirror module folder and execute `npm intall` in the module's directory.
```
cd ~/MagicMirror/modules
git clone https://github.com/bugsounet/EXT-Volume
cd EXT-Volume
npm install
```

# Configuration
To use this module, insert this in the config.js file of MagicMirror.

```js
{
  module: 'EXT-Volume',
  config: {
    debug: false,
    startSpeakerVolume: 100,
    startRecorderVolume: 50,
    syncVolume: false
  }
},
```

> | Option  | Description | Type | Default |
> | ------- | --- | --- | --- |
> | debug | enable or not debug mode | Boolean | false |
> | startSpeakerVolume | Set speaker volume on start in % | number | 100
> | startRecorderVolume | Set speaker volume on start in % | number | 50
> | syncVolume | Enable sync with system volume control (For multimedia keyboard keys or external mixer using) | Boolean | false |

# `EXT-TelegramBot` command
You can control `EXT-Volume` with EXT-TelegramBot
Available commands:
 * **/volume \<number>**: change the sound volume level. number is [0 - 100]
 * **/mute**: mute the speaker
 * **/unmute**: unmute the speaker
 * **/record \<number>**: change the mic level. number is [0 - 100]

# Developer Notes
## Incoming notification:
 * `EXT_VOLUME-SPEAKER_SET`: Set the speaker volume, payload is a number [0 - 100]
 * `EXT_VOLUME-SPEAKER_MUTE`: 
     * With payload `true`: mute the speaker.
     * With payload `false`: unmute the speaker
 * `EXT_VOLUME-SPEAKER_UP`: Will increase speaker volume by 5%
 * `EXT_VOLUME-SPEAKER_DOWN`: Will decrease speaker volume by 5%
 * `EXT_VOLUME-RECORDER_SET`: Set the recorder volume (Mic), payload is a number [0 - 100]
 * `EXT_VOLUME-RECORDER_UP`: Will increase recorder volume by 5%
 * `EXT_VOLUME-RECORDER_DOWN`: Will decrease recorder volume by 5%

## Outgoing notification:
 * `EXT_VOLUME-SPEAKER_GET`: Get the actual speaker volume level and return it in payload with a number [0 - 100]
 * `EXT_VOLUME-RECORDER_GET`: Get the actual recorder level and return it in payload with a number [0 - 100]
 
# Update
```
cd ~/MagicMirror/modules/EXT-Volume
npm run update
```

