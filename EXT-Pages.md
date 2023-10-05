---
title: EXT-Pages
description: 
published: true
date: 2023-10-05T16:05:49.203Z
tags: 
editor: markdown
dateCreated: 2022-10-13T20:03:12.399Z
---

# EXT-Pages

This [MagicMirror²][mm²] Module allows you to have animated pages in your magic mirror!<br>
Want to have more modules in your magic mirror, but want to keep the format?<br>
Or, want to have grouped modules that are themed together? Look no further!<br>

Note that this module does not provide any method of manually changing the page!<br>
You should ask other developers to add a notification to their modules, or add
one yourself!

> This modules use [EXT-Alert](/en/EXT-Alert) for displaying any errors
{.is-warning}

> This module is an Extented plugins for MMM-GoogleAssistant
{.is-info}

## ScreenShot
![Example](https://raw.githubusercontent.com/bugsounet/EXT-Pages/dev/example.webp)

## Installation

In your terminal, go to your MagicMirror's Module folder, Clone the repository and install it:

```bash
cd ~/MagicMirror/modules
git clone https://github.com/bugsounet/EXT-Pages
cd EXT-Pages
npm install
```

Configure the module in your config.js file.

## Using the module

To use this module, add it to the modules array in the `config/config.js` file.<br>
Note: module names used in the following example are fictitious.

```js
{
  module: "EXT-Pages",
  position: "bottom_bar",
  config: {
    pages: {
      0: [ "newsfeed" ],
      1: [ "calendar", "compliments" ]
    },
    fixed: [ "clock", "weather" ],
    hiddenPages: {
      "screenSaver": [ "clock", "MMM-SomeBackgroundImageModule" ],
      "admin": [ "MMM-ShowMeSystemStatsModule", "MMM-AnOnScreenMenuModule" ],
    },
    rotationTimes: {
      0: 20000
    },
    indicator: true,
    hideBeforeRotation: false,
    rotationTime: 15000,
    Gateway: {},
    loading: "loading.png"
  }
},

```

## Configuration options

| Option | Type | Default Value | Description |
| --- | --- | --- | --- |
| `pages`             | `{Number: [String...]...}` | `{}`                     | An Object String number of what each module should be on which page. Note that all entries must take their class name (e.g. this module's class name is `EXT-Pages`, while the default modules may just have `newsfeed`, without the `MMM-` or `EXT-` prefix. |
| `fixed`             | `[String...]`              | `[]`                     | Which modules should show up all the time. |
| `hiddenPages`       | `{String: [String...]...}` | `{}`                     | An Object defining special `hiddenPages` which are not available on the normal page rotation and only accassible via a notification. Modules defined in `fixed` are ignored and need to be also added if you wish to have them on any hidden page. |
| `animationTime`     | `int`                      | `1000`                   | Fading animation time. Set to `0` for instant change. Value is in milliseconds (1 second = 1000 milliseconds). |
| `rotationTime`      | `int`                      | `0`                      | Time, in milliseconds, between automatic page changes. |
| `rotationTimes`     | `{Number: String, ...}`    | `{}`                     | An Object with page number and associated delay times before changing page (will enforce `rotationTime` value) |
| `homePage`          | `int`                      | `0`                      | Which page index is the home page. If none is set, this returns to the leftmost page instead. |
| `indicator`         | `bool`                     | `true`                   | Activate page-indicator |
| `hideBeforeRotation` | `bool` | `false ` | Hide all modules before rotating except fixed. |
| `Gateway`           | `{String of plugins name: Number,... }` | `{}`        | Gateway rules for displaying plugins page automaticaly |
| `loading`  | `String` | `loading.png` | loading picture file name|

## Gateway Rules sample:
```
Gateway: {
  "EXT-Spotify": 1,
  "EXT-YouTube": 4,
  "EXT-MusicPlayer": 6,
  "EXT-RadioPlayer": 5
}
```
[Gateway](/en/Gateway) will search in this config what page displayed if a plugin is used.
Just inform the name of the plugin and associed page

It's only needed if you use module position (not on fullscreen)
So if you use Fullscreen mode, it's not necessary to inform this part and Gateway will just pause rotating inside of change page

## loading
Now `EXT-Pages` is able to hide all module on start
To prevent a black screen during `Gateway` loading, I have set an animated picture
Naturally, you can change !
Just upload it in `loading` directory and set the name of your picture in `loading` field
sample:
```
loading: "loading.png",
```
> Don't overwrite the default loading.png file
> Save it as your own filename !
{.is-warning}


## Hidden pages

The idea behind hidden pages is to be able to create special "modes" which
are totally configurable by the user and are seperated from the "normal" MM² operation.
Some examples would be a "guest", "admin" or "screensaver" mode, where only very
specific modules are shown and you do not want to have them in your normal page roation.

These hidden pages are only accessible via notifications, so you need to send them from
other modules. Examples integrations could be with touch, bots or voice commands.

## animate modules

Animation feature allows to define an animation to a module
Just use `animateIn` and `animateOut` feature in global modules configuration
See sample [there](https://develop.docs.magicmirror.builders/modules/configuration.html#animated) with `newsfeed` default module in `MagicMirror²` documentation

> If you don't want to define an animation to a module(s) and use default MagicMirror animation
{.is-info}

## `pages` with module name or with `classes` module definition

### with module name

That all entries must take their class name (e.g. this module's class name is `EXT-Pages`, while the default modules may just have `compliments`, `calendar`, ... without the `MMM-` or `EXT-` prefix. 

sample: 
```js
pages: {
 0: [ "calendar", "compliments", "EXT-Spotify" ]
```

### with `classes` module definition
You can also define a module `classes` and report it in `pages` feature
This feature can be used in case of multi-instance of a module

sample of configuration with default `weather` module:
```js
    {
      module: 'weather', // current weather
      classes: "Weather1 Weather2",
      disabled: false,
      position: 'top_right',
      config: {
        weatherProvider: 'openweathermap',
        type: 'current',
        location: 'New York',
        locationID: '5128581',
        apiKey: 'xxxx'
      }
    },
    {
      module: 'weather', // forecast weather
      classes: "Weather1 Weather3",
      disabled: false,
      position: 'top_right',
      header: 'Weather Forecast',
      config: {
        weatherProvider: 'openweathermap',
        type: 'forecast',
        location: 'New York',
        locationID: '5128581',
        apiKey: 'xxxx'
      }
    },
```

You will see `classes`
* `Weather1`: will call current and forecast weather
* `Weather2`: will call current weather ONLY
* `Weather3`: will call forecast weather ONLY

Let's apply some rules in `pages:{}`

```js
pages: {
 0: [ "Weather1", "calendar", "compliments" ],
 1: [ "Weather2",  "compliments" ],
 2: [ "Weather3", "calendar" ]
},
```

## `MMM-GoogleAssistant` recipe for vocal control
A prepared recipe is inclued and waiting for your use
Just add it in the config of MMM-GoogleAssistant

 * sample:
```js
recipes: [
  "../../EXT-Pages/recipe/EXT-Pages.js"
],
```
 * if you have other recipe, just add it like this:
```js
recipes: [
  "my_recipe.js",
  "../../EXT-Pages/recipe/EXT-Pages.js"
],
```
### How to use it ?

Activate your mirror with your prefered keyword and just say:
 - `go to main page`: will go to your main page
 - `go to page 1`: will go to your first [1] page
 - `go to page 2`: will go to the second [2] page 
 - `go to admin`: will go to the hidden page named `admin`

> This recipe is a sample, you can modify it and save it in another filename
{.is-warning}


## Notifications

The following is the list of notifications that EXT-Pages will handle:

| Notification | Payload type | Description |
| --- | --- | --- |
| `EXT_PAGES-CHANGED`      | `int`           | EXT-Pages will switch to the provided page index. |
| `EXT_PAGES-INCREMENT`    | `int`, Optional | EXT-Pages will increment the page, or by `n` times if a number is provided. Not providing a number is equivalent to sending a payload of `1`. If there are no more pages to increment by, this will loop around to the first page. |
| `EXT_PAGES-DECREMENT`    | `int`, Optional | EXT-Pages will decrement the page, or by `n` times if a number is provided. Not providing a number is equivalent to sending a payload of `1`. If there are no more pages to decrement by, this will loop around to the last page. |
| `EXT_PAGES-NUMBER`       | *None*          | EXT-Pages will respond with `EXT-PAGES_NUMBER_IS` with the current page index and total number pages. |
| `EXT_PAGES-PAUSE`        | *None*          | If EXT-Pages is set to rotate, this will pause rotation until a `RESUME_ROTATION` notification is sent. This does nothing if rotation was already paused. |
| `EXT_PAGES-RESUME`       | *None*          | If EXT-Pages was requested to pause rotation, this will resume automatic rotation. This does nothing EXT-Pages was not requested to pause. |
| `EXT_PAGES-HOME`         | *None*          | Return to the home page. If no home page is provided, return to the first page instead. |
| `EXT_PAGES-HIDDEN_SHOW`  | `String`        | EXT-Pages will switch to the provided hidden page name. |
| `EXT_PAGES-HIDDEN_LEAVE` | *None*          | EXT-Pages will leave the currently showing hidden page and return to the previous showing page index. |

The following is the list of notifications that EXT-Pages sends out:

| Notification          | Payload type | Description                                                                                                                                                         |
| --------------------- | ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `EXT-PAGES_NUMBER_IS` | `int`        | This notification is sent out on every page change and contains the current page index and total number pages. Sent in response to a `EXT_PAGES-NUMBER` notification|

sample of `EXT-PAGES_NUMBER_IS` response:
``` js
{
  Actual: <current page>,
  Total: <total number pages>
}
```

## Notes

This module keeps track of pages by their index rather than their page number,
so the leftmost page has an index of 0, the page to the right of that has an
index of 1, and the page to the right of that has an index of 2. Thus, to change
to the third page, your module should send out:

```js
this.sendNotification("EXT_PAGES-CHANGED", 2);
```
This module keeps internal track of how many pages you have, defined by your
config in the config file. There is no way to dynamically change the pages you
have. If there arises a need, please create an issue.

This module does not enforce how other modules represents or even responds to
EXT-Pages notifications.

## Updates

```js
cd ~/MagicMirror/modules/EXT-Pages
npm run update
```

## Credits
 * [@edward-shen](https://github.com/edward-shen) for [MMM-pages](https://github.com/edward-shen/MMM-pages) and [MMM-page-indicator](https://github.com/edward-shen/MMM-page-indicator)
 * @bugsounet