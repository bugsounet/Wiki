---
title: Configuration
description: 
published: true
date: 2024-05-19T08:53:36.753Z
tags: 
editor: markdown
dateCreated: 2022-03-14T17:46:14.577Z
---

> `MMM-GoogleAssistant` is not compatible with [`MMM-Remote-Control`](https://github.com/Jopyth/MMM-Remote-Control)
> You can use [`EXT-TelegramBot`](https://github.com/bugsounet/EXT-TelegramBot) for controling `MagicMirror`
{.is-danger}


# MMM-GoogleAssistant Configuration

use `config.js` file of MagicMirror for configuring MMM-GoogleAssistant

Don't panic !

MMM-GoogleAssistant have the new MagicMirror technology embed.<br>
We will apply it ;)

MMM-GoogleAssistant have his own default config in main core<br>

You have just to copy past the new needed part and new needed feature to change !<br>
MMM-GoogleAssistant will merge automaticaly with your new needed feature :)

> You don't have to copy/past all part (because it's already in main core)<br>
> You don't need to use all of these, Because all of them be set as default value.
> Just pick what you need then override in your `config.`<br>
> Just use and activate what you need to use!
{.is-warning}


# Simple
```js
{
  module: "MMM-GoogleAssistant",
  configDeepMerge: true,
  config: {
    assistantConfig: {
      latitude: 51.508530,
      longitude: -0.076132,
    }
  }
},
```

# Template

```js
{
  module: "MMM-GoogleAssistant",
  configDeepMerge: true,
  config: {
    debug: false,
    stopCommand: "stop",
    otherStopCommands: [],
    assistantConfig: {},
    responseConfig: {
      chimes: {},
      imgStatus: {},
      zoom: {}
    },
    recipes: []
  }
},
```
## Magic `configDeepMerge` tool for creating your personal configuration !

For creating your own configuration, MMM-GoogleAssistant will merge default core configuration and your needed configuration<br>
Just copy the Template and change with your needed value in named field (inside `{}`)<br>

> Notes:
  If you have some empty field with `{}`, you can delete it !
{.is-info}

* Just copy/past your needed configuration part in your config.
* You don't have to copy/past all!
* Copy/past ONLY what you want activate or change
* See Localisation in the template, if you want to change something, just past it your config

> **If you don't use a feature or a field: Don't past it in the config.**
> **All sample values are already in main core of MMM-GoogleAssistant**
{.is-warning}

> Don't be stupid !
> Don't copy/past some parts without modify anything !
> Why ?
> It's already enabled in main core!
{.is-danger}

# Configuration Details

## Field in `root` of config
> Display needed value for debug mode
{.is-info}


### Template Localisation

```js
config: {}
```

### Sample

```js
  config: {
    debug:false,
    stopCommand: "stop",
    otherStopCommands: []
  }
```

### Details

> |field | type | default value
> |---|---|---
> |debug | BOOLEAN | false
> |stopCommand | STRING | stop
> |otherStopCommands | Array of String | [ ]

- `debug` : When you set `debug` to `true`, detailed log will be recorded. When you don't want log, set it to `false`
- `stopCommand` : Command to say if you want to stop all plugins (EXT_ modules) playing
- `otherStopCommands` : Allow to use other/multi keywords for stopCommand using. It must be defined in array

> **otherStopCommands sample:**
>
> You want to define `stoppe`, `annuler`, `thank you` keywords in addition of default stopCommand
{.is-info}


```js
otherStopCommands: [ "stoppe", "annuler", "thank you" ]
```

> Just make your own keywords for your global stop command list!
{.is-success}

## Field `assistantConfig: {}`
> Define your localisation, language, define if assistant is registred to GoogleHome
{.is-info}

### Template Localisation

```js
config: {
  assistantConfig: {},
}
```


### Sample
```js
    assistantConfig: {
      lang: "en-US",
      latitude: 51.508530,
      longitude: -0.076132,
      deviceRegistred: false
    },
```

### Details

> |field (- subFiled) | type | default value
> |---|---|---
> |assistantConfig |  OBJECT | `{ ... }`
> |- lang |TEXT | "en-US"
> |- latitude |NUMBER |51.508530
> |- longitude|NUMBER |-0.076132
> |- deviceRegistred|BOOLEAN | false

- `lang` : language of the assistant
- `latitude` & `longitude` : location of your MagicMirror installed.
- `deviceRegistred` : enable this feature if this module is registred in `Google Home app`

Change latitude and longitude value for your actual position.

This [website](https://latitudelongitude.org/) can help you to determinate it

>  Currently supported languages are:
> de-DE, en-AU, en-CA, en-GB, en-IN, en-US, fr-CA, fr-FR, it-IT, ja-JP, es-ES, es-MX, ko-KR, pt-BR
{.is-info}


[Google Supported Language Code](https://developers.google.com/assistant/sdk/reference/rpc/languages)

For another languages, some language could be understood but not guaranteed.

<br>

## Field `responseConfig: {}`
> How GoogleAssistant should respond
{.is-info}


### Template Localisation:
```js
config: {
  responseConfig: {},
}
```
### Sample
```js
    responseConfig: {
      // i'm not stupid !
      // i will not copy/past this part without modify anything !
      useFullscreen: false,
      responseOutputCSS: "response_output.css",
      screenOutputTimer: 5000,
      useChime: true,
      confirmationChime: true
    }
```

### Details

> |field (- subFiled) | type | default value
> |---|---|---
> |responseConfig | OBJECT | `{ ... }`
> |- useFullscreen |BOOLEAN| false
> |- responseOutputCSS |STRING | screen_output.css
> |- screenOutputTimer |NUMBER (ms) |5000
> |- useChime |BOOLEAN |true
> |- confirmationChime |BOOLEAN | true

- `useFullscreen`: Use MMM-GoogleAssistant fullscreen mode and hide all modules
- `responseOutputCSS` : CSS name for Google responseOutput controlling
- `screenOutputTimer` : Duration of response (since it's finishing). After this milliseconds, the response window will be hidden and the module will return to standby status.
- `useChime` : If you don't want the beeping on status changed, set this to `false`.
- `confirmationChime`: Emit a confirmation chime when google have understand your query

<br>

## Field `chimes: {}`
> This feature can change the native chime/sounds with your own
{.is-info}


### Template Localisation
```js
config: {
  responseConfig: {
    chimes: {},
  }
}
```
### Sample
```js
      chimes: {
        // i'm not stupid !
        // i will not copy/past this part without modify anything !
        beep: "beep.mp3",
        error: "error.mp3",
        continue: "continue.mp3",
        confirmation: "confirmation.mp3",
        open: "Google_beep_open.mp3",
        close: "Google_beep_close.mp3",
        warning: "warning.ogg"
      },
```

### Details

> Define new sound of the events
> Your new sound should be in the `resources` directory
> Don't use the same name like default (it will be erased on update!)
{.is-info}

<br>

## Field `imgStatus: {}`
> This feature can change the native status pictures with your own
{.is-info}


### Template Localisation:
```js
config: {
  responseConfig: {
    imgStatus: {},
  }
}
```
### Sample
```js
      imgStatus: {
        // i'm not stupid !
        // i will not copy/past this part without modify anything !
        hook: "hook.gif",
        standby: "standby.gif",
        reply: "reply.gif",
        error: "error.gif",
        think: "think.gif",
        continue: "continue.gif",
        listen: "listen.gif",
        confirmation: "confirmation.gif",
        information: "information.gif",
        warning: "warning.gif",
        userError: "userError.gif"
      },
```
### Details

> Define new pictures of the events
> Your new pictures should be in the `resources` directory
> Don't use the same name like default (it will be erased on update!)
{.is-info}

## Field `zoom: {}`
> Define the zoom of transcription and response popup
{.is-info}


### Template Localisation
```js
config: {
  responseConfig: {
    zoom: {},
  }
}
```
### Sample
```js
      zoom: {
        // i'm not stupid !
        // i will not copy/past this part without modify anything !
        transcription: "80%",
        responseOutput: "60%"
      }
```

### Details

Google Assistant have 2 output field named `transcription` and `responseOutput`:<br>
You can define the `zoom` in each part<br>

> |field (- subFiled) | type | default value
> |---|---|---
> |zoom |  OBJECT | { ... }
> |- transcription |STRING | 80%
> |- responseOutput |STRING | 60%

- `transcription`: zoom of the transcription
- `responseOutput`: zoom of the response of Google Server
<br>

## Field `recipes: []`
> Control MagicMirror with any recipes
{.is-info}


### Template Localisation

```js
config: {
  recipes: [],
},
```

### Sample

> Notes:
>   ** It's an example
>   ** There is no recipe loaded by default in main core of MMM-GoogleAssistant
>   ** If you have to modify content of the recipe, copy/past it in another file because updater will erase it !
{.is-info}


```js
    recipes: [
      "MyRecipe1.js",
      "MyRecipe2.js",
      "MyPreferedRecipe.js"
    ],
```

### Details

> |field | type | default value
> |---|---|---
> |recipes |ARRAY of TEXT | []

- `recipes` : The recipe is an extension file of this module. You can load recipes that you need with this field.

> You can make your own recipe for your purpose.
> Read more docs about that and look inside of `recipes` directory.
{.is-warning}

## Field `website: {}` (only for v6.x)

> Define your MMM-GoogleAssistant website configuration
{.is-info}

### Template Localisation

```js
config: {
  website: {},
},
```

### Sample
> Notes:
>   ** It's an example
>   ** For better security, best way don't use default username and password
{.is-info}

```js
website: {
  use: true,
  username: "admin",
  password: "admin",
  CLIENT_ID: null
}
```

> | Option  | Description | Type | Default |
> | ------- | --- | --- | --- |
> | use | enable or not `MMM-GoogleAssistant` website | Boolean | true
> | username | Define your username for login | String | admin
> | password | Define your password for login | String | admin
> | CLIENT_ID | Define your CLIENT_ID of your smarthome action (see Smarthome section) | String | null

### How Can I connect to MMM-GoogleAssistant website ?

MMM-GoogleAssistant website can be open with your browser
You have to know your ip address of your pi !
Sample:
 * If ip address of your pi is `192.168.0.200`

Open your browser with this address: `http://192.168.0.200:8081`
Your browser will open MMM-GoogleAssistant website :)
Now, just enter your credentials defined in website config ;)

> MMM-GoogleAssistant will inform you in logs of MagicMirror
>```sh
>[LOG]   [GA] Start listening on port 8081
>[LOG]   [GA] Available locally at http://192.168.0.200:8081
>[LOG]   [GA] MMM-GoogleAssistant and Website Ready!
>```

> With Internet, you can use it in remote too
>
> Just map your prefered incoming port to MMM-GoogleAssistant port (8081) of your pi !
> In this case, you can control MMM-GoogleAssistant over the world with another internet connexion, or with your phone wherever you are
{.is-info}

### SmartHome (Optional)
You want to control MMM-GoogleAssistant from google home app or from another google assistant device ?

Install [SmartHome](/MMM-GoogleAssistant/SmartHome) functionality
