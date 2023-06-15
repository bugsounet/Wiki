---
title: EXT-Selfies
description: 
published: true
date: 2023-06-15T20:03:19.695Z
tags: 
editor: markdown
dateCreated: 2022-11-23T20:07:43.308Z
---

It will allows to take selfies with a webcam.

This module is an Extented plugins for `MMM-GoogleAssistant`

In addition, you can use others EXT plugin to control it or add some pretty plugins:
 * `EXT-SelfiesSender`: For sending to TelegramBot, GooglePhotos or by mail your selfies result
 * `EXT-SelfiesFlash`: For turn on/off automaticaly a flash light
 * `EXT-SelfiesViewer`: For displaying your selfies result on the screen
 * `EXT-Alert`: For display some information or error on your screen (Optional)
 * `Gateway` for full control in harmony with all EXT components (For `MMM-GoogleAssistant` only)

# Installation
Clone the module into your MagicMirror module folder and execute `npm intall` in the module's directory.
```
cd ~/MagicMirror/modules
git clone https://github.com/bugsounet/EXT-Selfies
cd EXT-Selfies
npm install
```

# Configuration
> To display the module insert it in the config.js file.
{.is-info}


## Configuration
```js
{
  module: 'EXT-Selfies',
  position: 'top_left',
  config: {
    debug: false,
    captureWidth:1280,
    captureHeight:720,
    device: null,
    usePreview: true,
    previewWidth:640,
    previewHeight:360,
    displayButton: true,
    buttonStyle: 0,
    buttons: {
      1: "master.png",
      2: "halloween.png",
      3: "birthday.png",
      4: "christmas.png"
    },
    blinkButton: false,
    playShutter: true,
    resultDuration: 1000 * 10,
    autoValidate: true,
    counterStyle: 0,
    showResult: true
  }
},
```

## Detailed Configuration

> | Option  | Description | Type | Default |
> | ------- | --- | --- | --- |
> | debug | Enable or not the Debug mode| Boolean | false |
> | captureWidth | Width of captured image | Number | 1280 |
> | captureHeight | Height of captured image | Number | 720 |
> | device |Default camera name (see bellow) | String or null | null |
> | usePreview | Display webcam preview when taking selfie | Boolean | true |
> | previewWidth | Width of preview camera window | Number | 640 |
> | previewHeight | Height of preview camera window | Number | 360 |
> | displayButton | Display button to press for take a selfie | Boolean | true |
> | buttonStyle | Choose style of the button (see bellow) | Number or Array | 0 |
> | buttons | Define any buttons (see bellow) | Object | |
> | blinkButton | Need to Blink button? | Boolean | false |
> | playShutter | Play shooter when taking a selfie? | Boolean | true |
> | resultDuration | How long to display the selfie result? (in ms. default is 10 sec) | Number | 10000 |
> | autoValidate | Validate automaticaly the selfie (by using `false` it will use touch-screen functionality for validate) | Boolean | true |
> | counterStyle | Style of the count down before take a selfie (see bellow) | Number | 0 |
> | showResult | Show the result of the selfie | Boolean | true |

### device

> `device` feature is only used if `usePreview` is not used (`false`)
{.is-warning}

>  -> `null` value should works at 99% of case if you have only one intalled camera.
>  -> See the backend log to get your installed camera name (with debug mode activated)
>  -> `EXT-Selfies` will tell you the list of camera installed, just report it in `device`
>    sample: `device: "/dev/video1",`
{.is-info}

### buttons

You can configure your own button !
Just upload your new button in `resouces` directory of `EXT-Selfies`
Add it in your configuration
Sample:
```
    buttons: {
      1: "master.png",
      2: "halloween.png",
      3: "birthday.png",
      4: "christmas.png",
      5: "MyOwnButton.png" // this is my new button !
    },
```

### butonStyle

With this config, you have visual choice button!

* `butonStyle: 0,`: mini button with the result of font-awesome icon camera
* `butonStyle: 1,`:
![](https://raw.githubusercontent.com/bugsounet/EXT-Selfies/dev/resources/master.png)
* `butonStyle: 2,`: 
![](https://raw.githubusercontent.com/bugsounet/EXT-Selfies/dev/resources/halloween.png)
* `butonStyle: 3,`:
![](https://raw.githubusercontent.com/bugsounet/EXT-Selfies/dev/resources/birthday.png)
* `butonStyle: 4,`:
![](https://raw.githubusercontent.com/bugsounet/EXT-Selfies/dev/resources/christmas.png)

You can again choose some buttons and blink it one by one!
`butonStyle: [1,2,3,4]`
in this case, `EXT-Selfies` will display button 1 after button 2 after button 3 ... (with a blink)  

### counterStyle

we code some counter Style

`counterStyle: 0,`: It's the default count with a minimal animate
`counterStyle: 1,`: It's a google style counter (**full animated and need a pi4!**)
`counterStyle: 2,`: It's a counter by using a point and transform it to a number (**full animated and need a pi4!**) 
`counterStyle: 3,`: It's a counter based to moving number (animated)

Let's test it ... and see any visual :)

## `MMM-GoogleAssistant` recipe for vocal control
A prepared recipe is inclued and waiting for your use
Just add it in the config of `MMM-GoogleAssistant`

 * sample:
```js
recipes: [
  "../../EXT-Selfies/recipe/EXT-Selfies.js"
],
```
 * if you have other recipe, just add it like this:
```js
recipes: [
  "my_recipe.js",
  "../../EXT-Selfies/recipe/EXT-Selfies.js"
],
```

### How to use it ?

> **[EN]**
> activate your mirror with your prefered keyword and just say:
> `take a selfie`: Assistant will open a new window to take a selfie
{.is-info}

> **[FR]**
> Une commande est également disponible pour prendre un selfie.
> Il suffit d'activer votre assistant avec votre mot clé préféré et dire:
>  `prends un selfie`
{.is-info}

## Developer Notes

- This module broadcasts:
 // @ToComplete //
- This module receive:
 // @ToComplete //

## Update
```sh
cd ~/MagicMirror/modules/EXT-Selfies
npm run update
```
