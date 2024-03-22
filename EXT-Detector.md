---
title: EXT-Detector
description: 
published: true
date: 2024-03-22T23:22:31.132Z
tags: 
editor: markdown
dateCreated: 2022-03-05T16:40:36.743Z
---

# Welcome to the EXT-Detector wiki!

> multi-keyword listener for MMM-GoogleAssistant
{.is-info}

* ***Used Technology:***
    * Snowboy Features
    * Porcupine Features

* ***It will include:***
    * Ok Google
    * Hey Google
    * Jarvis
    * Hey Siri
    * Computer
    * ...

# Installation

> I have created automatic installer for RaspberryPi and Linux Debian machines.
> Auto install script will propose to install needed dependencies.
{.is-info}

> For OSX machines, auto install script is not yet implented.
> So, manuel installation is nedeed and no help will be given for this
{.is-warning}

## Auto install (for RaspberryPi or Debian Linux machines only)
```sh
cd ~/MagicMirror/modules
git clone https://github.com/bugsounet/EXT-Detector

cd EXT-Detector
npm install
```
 * No other `npm` commands (e.g. npm audit fix) are needed after installation (they can break package dependencies)!

# EXT-Detector Configuration

> use config.js file of MagicMirror for configuring EXT-Detector
{.is-info}


## Default configuration

> This default configuration will enable automaticaly `snowboy` and `porcupine` features for listening this keyword:
> 
> ** `jarvis` for activate MMM-GoogleAssistant (with snowboy feature)
> ** `ok google` for activate MMM-GoogleAssistant (with porcupine feature)
> ** `hey google` for activate MMM-GoogleAssistant (with porcupine feature)
{.is-info}

```js
{
  module: "EXT-Detector",
  position: "top_left",
  configDeepMerge: true
},
```

## Configuration sample

> This complete config is reserved for tunning.
> The result is the same like default configuration
> See Configuration Structure for more informations
{.is-info}

```js
{
  module: "EXT-Detector",
  position: "top_left",
  config: {
    debug: false,
    useIcon: true,
    porcupineAccessKey: null,
    porcupineCustomModel: null,
    detectors: [
      {
        detector: "Snowboy",
        Model: "jarvis",
        Sensitivity: null
      },
      {
        detector: "Porcupine",
        Model: "ok google",
        Sensitivity: null
      },
      {
        detector: "Porcupine",
        Model: "hey google",
        Sensitivity: null
      }
    ]
  }
}
```

> If you want only Jarvis for activating GoogleAssistant
> Just delete all detector in Array but not `Jarvis`

And Naturally, this is sample of result with `Javis` keyword only for activate GoogleAssistant

```js
{
  module: "EXT-Detector",
  position: "top_left",
  config: {
    debug: false,
    detectors: [
      {
        detector: "Snowboy",
        Model: "jarvis",
        Sensitivity: null
      }
    ]
  }
}
```

> For using porcupine hotwords you need an AccessKey from [picovoice.ai](https://picovoice.ai/) website
{.is-warning}

> Now you have understand how `detectors: []` works, you can create your own
{.is-info}


# Configuration Structure

Explanation of all the features

## debug
> Display needed value for debug mode
{.is-info}

### Sample

```js
  config: {
    debug: false,
  }
```

### Details

> |field | type | default value
> |---|---|---
> |debug | BOOLEAN | false


When you set `debug` to `true`, detailed log will be recorded. When you don't want log, set it to `false`
<br>

## useIcon
>Display Google Icon on screen
{.is-info}

> Tip: You can set this feature to `false` when you use `EXT-Touch` plugin
{.is-info}

### Sample
```js
  config: {
    useIcon: true,
  }
```


### Details

> |field | type | default value
> |---|---|---
> |useIcon | BOOLEAN | true

`useIcon`: Activate display of logo and animate it when keyword discover

> You don't have to copy this sample in your config (already in EXT-Detector main core)
> You have just to copy this feature only if you want to desactivate it (with `false` value)
{.is-warning}

## porcupineAccessKey (optional)

> If you want to use Porcupine features,
> You need to register an Free account on [picovoice.ai](https://picovoice.ai/)
> When done, on your account, you will discover your `AccessKey`
{.is-info}

### Details
> |field | type | default value
> |---|---|---
> |porcupineAccessKey | String | null

`porcupineAccessKey`: past your AccessKey from picoVoice.ai account

### sample
```js
  config: {
    porcupineAccessKey: "myencodedAccessKeyFromPicovoice.ai",
  }
```
Just past your AccessKey like sample :)

## porcupineCustomModel
> You can create your own hotword for Porcupine from your picovoice.ai account
> You have to use `Model: "Custom"` in the Detectors array (see sample below)
{.is-info}

### Details
> |field | type | default value
> |---|---|---
> |porcupineCustomModel | String | null

`porcupineCustomModel`: name of the file of your custom model

> Unzip and copy (and renane if you want) the `.ppn` (custom model file) file into the `custom` folder of `EXT-Detector`
{.is-success}

> Warn: when you create your own custom model, choose `en` language for create it
> Other natural language will be coded soon
{.is-warning}


### sample
```js
  config: {
   porcupineCustomModel: "ispecedicounasse.ppn",
  }
```

In this sample, i have create an custom model named: `ispecedicounasse.ppn`

## detectors: []
> Keywords listener configuration
{.is-info}

### Sample
```js
  config: {
    detectors: [
      {
        detector: "Snowboy",
        Model: "jarvis",
        Sensitivity: null
      },
      {
        detector: "Porcupine",
        Model: "ok google",
        Sensitivity: null
      },
      {
        detector: "Porcupine",
        Model: "hey google",
        Sensitivity: null
      }
    ],
  }
```
### Details

> |field | type |
> |---|---|---
> | detectors | Array |
> |-detector| STRING | 
> |-Model | STRING |
> |-Sensitivity | NUMBER

detectors is an array of listener, you can add any detector and any keyword as you want !

`detector`: the detector Program Name to use `Snowboy` or `Porcupine`

`Model`: name of the model (see below)

`Sensitivity`: Override default sensitivity value for applied model defined in Model. (see below)
Value could be within a range from 0.0 to 1.0. `null` will set default sensitivity.

### Model and default Sensitivity by detector program

> | detector | Model | Sensitivity
>  |---|---|---|---
>  | Snowboy | smart_mirror | 0.5
>  | Snowboy | jarvis | 0.7
>  | Snowboy | computer | 0.6
>  | Snowboy | snowboy |  0.5
>  | Snowboy | subex | 0.6
>  | Snowboy | neo_ya | 0.7
>  | Snowboy | hey_extreme | 0.6
>  | Snowboy | view_glass | 0.7
>  | Porcupine | americano | 0.7
>  | Porcupine | blueberry | 0.7
>  | Porcupine | bumblebee | 0.7
>  | Porcupine | computer | 0.7
>  | Porcupine | grapefruit | 0.7
>  | Porcupine | grasshopper | 0.7
>  | Porcupine | hey google | 0.7
>  | Porcupine | hey siri | 0.7
>  | Porcupine | jarvis | 0.7
>  | Porcupine | ok google | 0.7
>  | Porcupine | picovoice | 0.7
>  | Porcupine | porcupine | 0.7
>  | Porcupine | terminator | 0.7
>  | Porcupine | Custom | 0.7

# complete Sample with CustomModel with Porcupine

```js
{
  module: "EXT-Detector",
  position: "top_left",
  config: {
    porcupineAccessKey: "myencodedAccessKeyFromPicovoice.ai",
    porcupineCustomModel: "ispecedicounasse.ppn",
    detectors: [
      {
        detector: "Porcupine",
        Model: "custom",
        Sensitivity: null
      }
    ]
  }
}
```

> In this case, I have create an custom model for Porcupine `ispecedicounasse.ppn`
> For use it, use the `Model: "custom"` in the Detector array
{.is-success}



# Update of EXT-Detector
> If a new version of EXT-Detector is available
{.is-info}

```sh
cd ~/MagicMirror/modules/EXT-Detector
npm run update
```


# Update EXT-Detector if MagicMirror is updated (exemple MagicMirror v2.21.x to v2.22.x)

> This command can help also if any problem on EXT-Detector (it's equal to make a complete reinstall of this module)
{.is-info}


```sh
cd ~/MagicMirror/modules/EXT-Detector
npm run rebuild
```

# Notes:
>  ** No other `npm` commands are needed after installation (it can brake dependencies) !
>  ** Do NOT use ANY MagicMirror module to update EXT-Detector dependencies and this module !
{.is-warning}
