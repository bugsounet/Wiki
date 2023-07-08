---
title: EXT-Screen
description: 
published: true
date: 2023-07-08T20:24:12.257Z
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
 * `EXT-Updates`: For update automaticaly this module (Optional)
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
    mode: 1,
    displayCounter: true,
    displayBar: true,
    displayStyle: "Text",
    displayLastPresence: true,
    lastPresenceTimeFormat: "LL H:mm",
    displayAvailability: true,
    detectorSleeping: false,
    gpio: 20,
    clearGpioValue: true,
    sound: false,
    touchMode: 3,
    ON: [],
    OFF: []
  }
},
```

## Detailed Configuration

> | Option  | Description | Type | Default |
> | ------- | --- | --- | --- |
> | animateBody | Animate MagicMirror on turn on/off the screen | Boolean | true |
> | delay | Time before the mirror turns off the display if no user activity is detected. (in ms) | Number | 120000 |
> | mode | mode for turn on/off your screen (see bellow) | number | 1 |
> | displayCounter | Should display Count-down in screen ? | Boolean | true |
> | displayBar| Should display Count-up bar in screen ? | Boolean | true |
> | displayStyle| Style of the Count-down. Available: "Text", "Line", "SemiCircle", "Circle", "Bar" | String | Text |
> | displayLastPresence| Display the date of the last user presence | Boolean | true |
> | lastPresenceTimeFormat| Change the date format (moment.js format) of the last presence | String | LL H:mm |
> | displayAvailability| Display screen availability time (average 24h)| Boolean | true |
> | detectorSleeping | Activate EXT-Detector only when display is on | Boolean | false |
> | gpio| GPIO number for control the relay (mode 6 only) | Number | 20 |
> | clearGpioValue| reset GPIO value script of relay (mode 6 and 7 only) | Boolean | true |
> | sound| emit a sound when your screen turn on/off | Boolean | false |
> | touchMode | Selected mode for enable/disable the screen with touch (see below) | number | 3 |
> | ON | Defined cron ON display time (see below) | Array of object | []
> | OFF | Defined cron OFF display time (see below) | Array of object | []

### Available mode:
   - `mode: 1` - use vgencmd (RPI only)
   - `mode: 2` - use dpms (RPI version)
   - `mode: 3` - use tvservice (RPI only)
   - `mode: 4` - use HDMI CEC
   - `mode: 5` - use dpms (linux version for debian, ubuntu, ...)
   - `mode: 6` - use a relay switch command controled by GPIO
   - `mode: 7` - use a relay switch command controled by GPIO with python (read reverse values)
   - `mode: 8` - use ddcutil
   - `mode: 0` - disabled mode and disable turnOffDisplay too
   
### Available touchMode:
   - `touchMode: 0`
     - disabled
   - `touchMode: 1`
     - One click on the screen will restart the timer (or Wake up the screen if needed)
     - Double Click on the screen will shutdown the screen
   - `touchMode: 2`
     - One Click on the EXT-Screen area will restart the timer
     - Long Click on the screen will shutdown or wake up the screen (toogle)
   - `touchMode: 3`
     - One Click on the EXT-Screen area will restart the timer
     - Doucle Click on the EXT-Screen area will shutdown the screen
     - One Click on the screen will wake up if shutdown

### `ON: []` and `OFF: []`
> This is the rule to Turn ON et Turn OFF your screen
{.is-info}

Each event have an object format:
```js
{
  dayOfWeek: <Array of days>,
  hour: <hour>,
  minute: <minute>
}
```

dayOfWeek is an array of number
This number define the day:
> `0`: Sunday
> `1`: Monday
> `2`: Tuesday
> `3`: Wednesday
> `4`: Thursday
> `5`: Friday
> `6`: Saturday
{.is-success}


#### Sample
sample if you want to create an event from Monday to Thursday at 07h45:

```js
{
  dayOfWeek: [1,2,3,4,5],
  hour: 45,
  minute: 45
}
```

sample if you want to create an event every Friday at 08h00

```js
{
  dayOfWeek: [5],
  hour: 00,
  minute: 08
}
```

sample if you want to create an event from Monday to Friday at 17h00
```js
{
  dayOfWeek: [1,2,3,4,5],
  hour: 17,
  minute: 00
}
```

### Create ON/OFF events

Let's create ON and OFF now
I want to apply this rules: 

---> Screen is ON:
 * from Monday to Thursday at 07h45
 * every Friday at 08h00
   
So, `ON` rules will be:

```js
ON: [
  {
    dayOfWeek: [1,2,3,4,5],
    hour: 45,
    minute: 45
  },
  {
    dayOfWeek: [5],
    hour: 00,
    minute: 08
  }
],
```

---> Screen is OFF
  * from Monday to Friday at 17h00

So, `OFF` rules will be:

```js
OFF: [
  {
    dayOfWeek: [1,2,3,4,5],
    hour: 17,
    minute: 00
  }
]
```

> Let's apply your own rules !
{.is-success}

> When `ON` event started: counter will be not displayed
> When `OFF` event started: counter will be functional and turn off the screen when done
{.is-warning}


## Developer Notes

- This plugin broadcasts:
  * `EXT_SCREEN-POWER` with payload: `true` when your screen turn on or `false` when your screen turn off.

- This plugin receive:

  * `EXT_SCREEN-END` notification to force the end of the count down
  * `EXT_SCREEN-WAKEUP` notification to wake up the screen and reset count down
  * `EXT_SCREEN-LOCK` notification keep the screen on and lock it (freeze counter and stop pir detection) 
  * `EXT_SCREEN-UNLOCK` notification unlock the screen and restart counter and pir detection
  * `EXT_SCREEN-FORCE_END` notification to force turn off your screen (and stop counter and pir detection)
  * `EXT_SCREEN-FORCE_WAKEUP` notification to force turn on your screen (restart counter and pir detection)

> Note: `EXT_SCREEN-FORCE_END` wait `EXT_SCREEN-FORCE_WAKEUP` **ONLY** for wakeup the screen
{.is-warning}


## Update
```sh
cd ~/MagicMirror/modules/EXT-Screen
npm run update
```
