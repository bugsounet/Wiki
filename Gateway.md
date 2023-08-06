---
title: Gateway
description: 
published: true
date: 2023-08-06T10:29:49.615Z
tags: 
editor: markdown
dateCreated: 2022-02-27T00:21:25.618Z
---

> `MMM-GoogleAssistant` need an gateway for comunicate with plugins.
> So `Gateway` will doing this job !
{.is-info}

# Why `Gateway` is needed ?

When you use an some media modules  (music, video, photos,...) some weird things can happen
I think, many people have this problem:
 * I can run 2 media modules at the time
 * pir sensor don't detect media... so screen turn off
 
So `Gateway` is your friend

Gateway is able to:
 * Lock your screen when a plugins is playing and prohibit going into sleep mode
 * Prohibit to use 2 plugins in sametime (can't listen Spotify and watch YouTube at the same time for exemple)
 * Turn off all not needed plugins and keep the last plugin demand
 * Unlock your screen and return in normal mode when no plugins are used
 * Read MMM-GoogleAssistant response and launch automaticaly a plugins (photo, browser, youtube...)


All name of `MMM-GoogleAssistant` plugins start with `EXT` and the `Gateway` will apply many rules for make deal between `MMM-GoogleAssistant` and plugins

`Gateway` have a database of ALL `EXT` plugins for apply self rules.

`MMM-GoogleAssistant` 💭 -> Gateway 🎼 <-> EXT plugins 🎹

Gateway is a real conductor 🙂

# Gateway

  Gateway has an embedded application.
  This application is available directly through your browser.
  It can be used locally or remotely over the internet.
 
  * Allows to Install / delete all EXT plugins
  * Allows to configure / modify your EXT with a template
  * Allows to configure MagicMirror
  * Allows you to create a backup of your configuration file at each modification
  * Displaying Magic Mirror Logs in real time
  * Allows you to do now operations with the embedded Terminal
  * Allows you to manually restart or stop MagicMirror
  * Allows you to turn off or turn on your screen
  * ...

  Gateway have also an embedded smarthome controler !

  * Able to control:
    * EXT-Screen
    * EXT-Pages
    * EXT-Spotify
    * EXT-Volume
    * ...
  * Controling MagicMirror from GoogleHome app (smartphone)
  * Controling Magicmirror from any google assistant device

# Screenshots of the app
![plugin_manager.png](/resources/gateway/plugin_manager.png)
![terminal.png](/resources/gateway/terminal.png)
![mmconfig.png](/resources/gateway/mmconfig.png)
![tools.png](/resources/gateway/tools.png)
![setting.png](/resources/gateway/setting.png)

# Your System is under Control
![sysinfo1.jpg](/resources/gateway/sysinfo1.jpg)
![sysinfo2.jpg](/resources/gateway/sysinfo2.jpg)


# Screenshot of the google home app (smartphone)

### Google Home `Jarvis` icon:
![jarvis.png](/resources/smarthome/jarvis.png)

### On the App:
![app1.png](/resources/smarthome/app1.png)

![app2.png](/resources/smarthome/app2.png)

![app3.png](/resources/smarthome/app3.png)

![app4.png](/resources/smarthome/app4.png)

# Installation

Clone the module into your MagicMirror module folder and execute `npm intall` in the module's directory.
```
cd ~/MagicMirror/modules
git clone https://github.com/bugsounet/Gateway
cd Gateway
npm install
```

# Configuration
> insert your configuration in the config.js file of MagicMirror.
{.is-info}

```js
{
  module: "Gateway",
  config: {
    debug: false,
    username: "admin",
    password: "admin",
    CLIENT_ID: null
  }
},
```

> | Option  | Description | Type | Default |
> | ------- | --- | --- | --- |
> | debug | Enable debug mode | Boolean | false |
> | username | Define your username for the app | String | admin
> | password | Define your password for the app | String | admin
> | CLIENT_ID | Define your CLIENT_ID of your smarthome action (see Smarthome section) | String | null
> All settings of Gateway can be modified with the app
{.is-success}

# How Can I connect to the app ?

Gateway app can be open with your browser
You have to know your ip address of your pi !
Sample:
 * If ip address of your pi is `192.168.0.200`

Open your browser with this address: `http://192.168.0.200:8081`
Your browser will open the Gateway app :)
Now, just enter your credentials defined in config ;)

> Gateway will inform you in log of MagicMirror 
> `[LOG]   [GATEWAY] Start listening on port 8081`
> `[LOG]   [GATEWAY] Available locally at http://192.168.0.200:8081`
{.is-success}

> With Internet, you can use it in remote too
>
> Just map your prefered incoming port to Gateway port of your pi !
> In this case, you can control Gateway over the world with another interet connexion, or with your phone wherever you are
{.is-info}

# SmartHome (Under Writing)
You want to control `Jarvis` from google home app or from another google assistant device ?

  * Introduction
  * Installation
  * Google Action Configuration

# Update
```
cd ~/MagicMirror/modules/Gateway
npm run update
```

# Reinstall
> For reinstall this plugin, you can use this command:
{.is-info}

```
cd ~/MagicMirror/modules/Gateway
npm run rebuild
```

# Thanks to translators

* @CalcU: for Spanish
* @lxne: for German
* @bitass: for Dutch
* @pitchx: for French review

