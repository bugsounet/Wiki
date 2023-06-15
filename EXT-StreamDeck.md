---
title: EXT-StreamDeck
description: 
published: true
date: 2023-05-19T09:31:04.637Z
tags: 
editor: markdown
dateCreated: 2022-12-10T23:00:43.002Z
---

# EXT-StreamDeck

This plugin allows to control your mirror with stream Deck by [elgato©](https://www.elgato.com/)

![](https://raw.githubusercontent.com/bugsounet/EXT-StreamDeck/dev/resources/streamDeck.png)

![](https://raw.githubusercontent.com/bugsounet/EXT-StreamDeck/dev/resources/sample.jpg)

## Testing Video

This is a demo in [video](https://www.youtube.com/watch?v=YC1t6Ae7HWM) (sorry for quality)

## Installation

To install this plugin, try this command:

```sh
cd ~/MagicMirror/modules/
git clone https://github.com/bugsounet/EXT-StreamDeck
cd EXT-StreamDeck
npm install
```

> For displaying any errors or informations `EXT-Alert` is recommanded
{.is-warning}

## Prepare using StreamDeck
Some linux rules are needed.
Let's set it !
```sh
cd ~/MagicMirror/modules/EXT-StreamDeck
npm run setup
```
And reboot your pi

## Configuration sample

```js
{
  module: 'EXT-StreamDeck',
  config: {
    debug: false,
    device: null,
    Brightness: 100,
    EcoBrightness: 10,
    EcoTime: 10000,
    keyFinder: false,
    keys: [
      {
        key: 0,
        logo: "tv-on",
        notification: "EXT_SCREEN-WAKEUP",
        payload: null,
        command: null,
        sound: "opening"
      },
      {
        key: 1,
        logo: "spotify",
        notification: "EXT_SPOTIFY-PLAY",
        payload: null,
        command: null,
        sound: "opening"
      },
      {
        key: 2,
        logo: "volume-up",
        notification: "EXT_VOLUME-SPEAKER_UP",
        payload: null,
        command: null,
        sound: "up"
      },
      {
        key: 3,
        logo: "tv-off",
        notification: "EXT_SCREEN-END",
        payload: null,
        command: null,
        sound: "closing"
      },
      {
        key: 4,
        logo: "stop",
        notification: "EXT_STOP",
        payload: null,
        command: null,
        sound: "closing"
      },
      {
        key: 5,
        logo: "volume-down",
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
> | device | Path of the StreamDeck to use. null = the default| String or null | null|
> | Brightness | Set the brightness of the streamDeck| Number | 100|
> | EcoBrightness | Set standby brightness | Number | 10 |
> | EcoTime | Delay before standby (in ms) | Number | 10000 |
> | keyFinder | Display keycode with EXT-Alert when a key is pressed| Boolean | false |
> | keys | Define your keys rules (see bellow)| Array | |

> **device:** Generaly `null` value will use the first streamDeck found
> If not works, you can discover the list of the streamDeck in backlog by activate `debug` mode
> `[STREAMDECK] Found model: mini Path: /dev/hidraw0 serialNumber: BL36H1A06XXX`
> Just report the path. in this case: `/dev/hidraw0`
{.is-info}

### keys

`keys` is an array of params for control your mirror
this array need `keyCode`, `notification`, `payload`, `command` and `sound` parameter

> | Option  | Description | Type |
> | ------- | --- | --- |
> | key | Key number. You can catch it with keyFinder activated | Number
> | logo | Set the logo to display (only in png) | String
> | notification | Notification to send | String
> | payload | Payload associated to notification (optional) | String
> | command | Shell command to execute (optional) | String
> | sound | Name of the sound when executed (mp3 only) | String

>  **key**: Can be discover when you activate keyFinder
>   Just press a key and `EXT-Alert` will say the associated keyCode
>   Naturally, report it in this field
{.is-info}

>  **logo**: logo name located in `resources` directory (without extension)
  **Notes:**
   If you want more logo, just see in the `icons-Sample` directory !
   Just past the new logo in the resources directory and use it!
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
>   **Note: you can add your own mp3 too!**
{.is-info}
  
## Update
```sh
cd ~/MagicMirror/modules/EXT-StreamDeck
npm run update
```