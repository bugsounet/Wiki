---
title: EXT-Screen
description: 
published: true
date: 2023-06-15T20:02:47.727Z
tags: 
editor: markdown
dateCreated: 2022-02-25T00:04:52.369Z
---

After a configurated time without any user interaction the display will turn off and hide all modules for economy mode.

This module is an Extented plugins for `MMM-GoogleAssistant`

In addition, you can use others EXT modules to control it or add some pretty plugins:
 * `EXT-Pir`: For PIR Sensor using
 * `EXT-Governor`: For Manage your CPU
 * `EXT-Motion`: For detecting all motions with a webcam (optional)
 * `EXT-ScreenManager`: For automaticaly turn ON and Turn OFF your screen with defined hours (optional)
 * `EXT-ScreenTouch`: For turn on/off your screen with touch screen (optional)
 * `EXT-UpdateNotification`: For update automaticaly this module (Optional)
 * `EXT-Alert`: For display some information or error on your screen (Optional)
 * `Gateway` for full control in harmony with all EXT components (For `MMM-GoogleAssistant` only)

# Screenshot
![](https://raw.githubusercontent.com/bugsounet/EXT-Screen/dev/screenshot/screenshot.png)

![](https://raw.githubusercontent.com/bugsounet/EXT-Screen/dev/screenshot/screenshot2.png)

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
  position: 'top_left',
  config: {
    delay: 2 * 60 * 1000
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
  position: 'top_left',
  config: {
    debug: false,
    animateBody: true,
    delay: 2 * 60 * 1000,
    turnOffDisplay: true,
    mode: 1,
    ecoMode: true,
    displayCounter: true,
    displayBar: true,
    displayStyle: "Text",
    displayLastPresence: true,
    lastPresenceTimeFormat: "LL H:mm",
    detectorSleeping: false,
    autoHide: true,
    delayed: 0,
    gpio: 20,
    clearGpioValue: true,
    sound: false
  }
},
```

## Detailed Configuration

> | Option  | Description | Type | Default |
> | ------- | --- | --- | --- |
> | animateBody | Animate MagicMirror on turn on /off the screen | Boolean | true |
> | delay | Time before the mirror turns off the display if no user activity is detected. (in ms) | Number | 120000 |
> | turnOffDisplay | Should the display turn off after timeout? | Boolean | true |
> | mode | mode for turn on/off your screen (see bellow) | number | 1 |
> | ecoMode | Should the MagicMirror hide all module after timeout ? | Boolean | true |
> | displayCounter | Should display Count-down in screen ? | Boolean | true |
> | displayBar| Should display Count-up bar in screen ? | Boolean | true |
> | displayStyle| Style of the Count-down. Available: "Text", "Line", "SemiCircle", "Circle", "Bar" | String | Text |
> | displayLastPresence| Display the date of the last user presence | Boolean | true |
> | lastPresenceTimeFormat| Change the date format (moment.js format) of the last presence | String | LL H:mm |
> | detectorSleeping | Activate EXT-Detector only when display is on | Boolean | false |
> | autoHide | Auto Hide this module when the lock function is activated | Boolean | true |
> | delayed| Delayed turn on screen time (only if your screen is off). (in ms) | Number | 0 |
> | gpio| GPIO number for control the relay (mode 6 only) | Number | 20 |
> | clearGpioValue| reset GPIO value script of relay (mode 6 only) | Boolean | true |
> | sound| emit a sound when your screen turn on/off | Boolean | false |

 * Available mode:
   - `mode: 1` - use vgencmd (RPI only)
   - `mode: 2` - use dpms (version RPI)
   - `mode: 3` - use tvservice (RPI only)
   - `mode: 4` - use HDMI CEC
   - `mode: 5` - use dpms (linux version for debian, ubuntu, ...)
   - `mode: 6` - use a relay switch command controled by GPIO
   - `mode: 0` - disabled mode and disable turnOffDisplay too

## Developer Notes

- This module broadcasts:

  * `EXT_SCREEN-ON` notification when your screen turn on.
  * `EXT_SCREEN-OFF` notification when your screen turn off. 
- This module receive:

  * `EXT_SCREEN-END` notification to force the end of the count down
  * `EXT_SCREEN-WAKEUP` notification to wake up the screen and reset count down
  * `EXT_SCREEN-LOCK` notification keep the screen on and lock it (freeze counter and stop pir detection) 
  * `EXT_SCREEN-UNLOCK` notification unlock the screen and restart counter and pir detection

## Update
```sh
cd ~/MagicMirror/modules/EXT-Screen
npm run update
```

 