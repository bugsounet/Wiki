---
title: MMM-Netatmo-Thermostat
description: 
published: true
date: 2022-03-22T06:12:42.600Z
tags: 
editor: markdown
dateCreated: 2022-01-27T13:13:05.462Z
---

# MMM-Netatmo-Thermostat

This module display your Netatmo Thermostat informations on your mirror

## Screenshoot
![](https://camo.githubusercontent.com/b3e7f966f574fabf1c9dc7b2f98557799c2d9e1c06f41ca1ac3d3d0781387ae2/68747470733a2f2f666f72756d2e627567736f756e65742e66722f6173736574732f75706c6f6164732f66696c65732f313634333134323239383536302d37373761653835612d376135342d343038642d613261332d6432643632663766343238322d696d6167652e706e67)

![](https://camo.githubusercontent.com/783ddadfc32397f588a998cc19f2fa51883a39a4eae612fd9f58718d88213d86/687474703a2f2f666f72756d2e627567736f756e65742e66722f6173736574732f75706c6f6164732f66696c65732f313634333134323337383136362d36333764326530332d383665342d346136372d626164622d6239316438323863373034612d696d6167652e706e67)

## Install

  ```sh
  cd ~/MagicMirror/modules
  git clone https://github.com/bugsounet/MMM-Netatmo-Thermostat
  cd MMM-Netatmo-Thermostat
  npm install
  ```

## Pre-install

   1) Link your module with netatmo api
      * Navigate to [Netatmo Connect](https://dev.netatmo.com/) website
      * You have to use your personnal identifier
      * Create a new app
      * Note your client id and client secret
      * naturaly, save it :)

   2) Create your own configuration
      * replace all value by yours
      * `home_id` will be null at this time
      * don't worry, we find it in post-install step !

## Configuration Sample

### Simple Sample

```js
    {
      module: 'MMM-Netatmo-Thermostat',
      position: 'top_center',
      configDeepMerge: true,
      config: {
        client_id: null,
        client_secret: null,
        username: null,
        password: null,
        home_id: null,        
      }
    },
```

### Personalized Sample

> This Configuration is the same like the Simple Configuration.
{.is-info}


If you want to tune it, you can change only the desired value

```js
    {
      module: "MMM-Netatmo-Thermostat",
      position: "top_center",
      configDeepMerge: true,
      config: {
        debug: false,
        client_id: "61e46d4161379201472XXXXX",
        client_secret: "7CX0nGvu5ov4A7rqEeo0UXXXXX",
        username: "adress@email",
        password: "mypassword",
        updateInterval: 60,
        home_id: null,
        room_id: 0,
        display: {
          fixed: false,
          name: true,
          mode: true,
          battery: true,
          firmware: true,
          signal: true,
          tendency: true
        }
      }
    },
```

### Configuration Structure

* Field in `root`

> |field | type | default | description
> |--- |--- |--- | ---
> |debug| BOOLEAN | false | enable or not debug mode
> |client_id| STRING | null | your client id of your app 
> |client_secret| STRING | null | your client secret of your app
> |username| STRING | null | your email adress of Netatmo account 
> |password| STRING | null | your password of Netatmo account
> |home_id| STRING | null | your home_id find with `npm run setup`
> |room_id| NUMBER | 0 | room_id (can help if your have many adapter) generaly, you don't have to change this value
> |updateInterval| NUMBER| 60 | delay in seconds for next update (mini interval is 30 seconds to preserve Netatmo Server)

* Field `display: {...}`

> |field | type | default | description
> |--- |--- |--- |---
> |fixed| BOOLEAN | false | Fix width of the module and don't strech it to follow others modules
> |name| BOOLEAN | true | Display the name of the thermostat
> |mode| BOOLEAN | true | Display the mode and associated the temperature
> |battery| BOOLEAN | true | Display the battery level of the thermostat
> |firmware| BOOLEAN | true | Display the firmware number
> |signal| BOOLEAN | true | Display signal quality between relay and thermostat
> |tendency| BOOLEAN | true | Display the temperature tentency arrow

## Post install: Find your `home_id`

  * For this the module configuration should be present in your `config.js` file
  * Naturraly, your MagicMirror apps should be stop at this point :)
  * Run this command:
  ```sh
  cd ~/MagicMirror/modules/MMM-Netatmo-Thermostat
  npm run setup
  ```
  This script will read your `config.js` file and find your module configuration.
  
  * Sample of Return with this script:
  ```sh
[NETATMO] Search config.js file...
[NETATMO] Found config.js !
[NETATMO] Search MMM-Netatmo-Thermostat...
[NETATMO] Skip: calendar
[NETATMO] Skip: alert
[NETATMO] Skip: clock
[NETATMO] Skip: MMM-TelegramBot
[NETATMO] Skip: MMM-GoogleAssistant
[NETATMO] Skip: MMM-Detector
...
[NETATMO] Found: MMM-Netatmo-Thermostat
[NETATMO] All needed value are there, perfect!
[NETATMO] Try to login to Netatmo Servers...
[NETATMO] Authenticated!
[NETATMO] Read result from Netatmo server (/homesdata Endpoint)...
[NETATMO] --> [Maison] home_id: "61e44c0f411341055bXXXXX"
[NETATMO] Select your 'home_id' key and past it in your config.
```

You can have multi ligne with home_id value (if you have another house with netatmo thermostat)
Select the better line !
Just copy/past the home_id key and past it in your config
In this case : `home_id: "61e44c0f411341055bXXXXX",`

## Update

  ```sh
  cd ~/MagicMirror/modules/MMM-Netatmo-Thermostat
  git pull && npm install
  ```
