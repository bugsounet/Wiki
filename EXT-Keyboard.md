---
title: EXT-Keyboard
description: 
published: true
date: 2024-12-31T00:45:05.393Z
tags: 
editor: markdown
dateCreated: 2022-12-10T22:00:00.139Z
---

# EXT-Keyboard

This plugin allows to control your mirror with a keyboard or a mini-keyboard

![](https://m.media-amazon.com/images/I/51pCVRjU16L._AC_.jpg)

## Installation

To install this plugin, try this command:

```sh
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run install:EXT-Keyboard
```

## Configuration sample

```js
{
  module: 'MMM-GoogleAssistant/EXTs/EXT-Keyboard',
  config: {
    debug: false,
    keyFinder: false,
    keys: [
      {
        keyCode: 107, // key + of the keyboard
        notification: "EXT_VOLUME-SPEAKER_UP",
        payload: null,
        command: null,
        sound: "up"
      },
      {
        keyCode: 109, // key - of the keybord
        notification: "EXT_VOLUME-SPEAKER_DOWN",
        payload: null,
        command: null,
        sound: "down"
      }
    ]  
  }
},
```

## Detailed Configuration

> | Option  | Description | Type | Default |
> | ------- | --- | --- | --- |
> | debug | Enable or not the Debug mode| Boolean | false |
> | keyFinder | Display keycode with MMM-GoogleAssitant Alert when a key is pressed| Boolean | false |
> | keys | Define your keys rules (see bellow)| Array | |

### keys

`keys` is an array of params for control your mirror
this array need `keyCode`, `notification`, `payload`, `command` and `sound` parameter

> | Option  | Description | Type |
> | ------- | --- | --- |
> | keyCode | KeyCode number. You can catch it with keyFinder activated | Number
> | notification | Notification to send | String
> | payload | Payload associated to notification (optional) | String
> | command | Shell command to execute (optional) | String
> | sound | Name of the sound when executed (mp3 only) | String

>  **keyCode**: Can be discover when you activate keyFinder
>   Just press a key and MMM-GoogleAssistant will say the associated keyCode
>   Naturally, report it in this field
{.is-info}

>  **notification**: Generaly each module/plugins have some incoming notification for a fonction.
>   Just past the notification name
{.is-info}

>  **payload**: If needed you can add a payload to the notification
{.is-info}

>  **command**: You want to execute an shell command (with python, bash, sh,...)
>   Your file must be in `scripts` directory
>   Sample: if you want to execute `test.sh`
>   command line is:
>   `command: "sh test.sh",`
{.is-info}

>  **sound**: If you want to play a sound, just see in the `resources` directory
>   all sound must be in `.mp3`
>   just past the name without extension
{.is-info}

  
## Update
```sh
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run update
```

## Uninstall
```sh
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run remove:EXT-Keyboard
```