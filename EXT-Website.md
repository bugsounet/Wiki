---
title: EXT-Website
description: 
published: true
date: 2024-12-31T00:19:02.691Z
tags: 
editor: markdown
dateCreated: 2024-05-19T12:29:02.415Z
---

# EXT-Website

  EXT-Website is an embedded application.
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

# Screenshots of the website

## EXT Plugin manager
![plugin_manager.png](/resources/googleassistant/plugin_manager.png)
## Terminal
![terminal.png](/resources/googleassistant/terminal.png)
## MagicMirror² Configuration
![mm_config.png](/resources/googleassistant/mm_config.png)
## Tools Box
![toolsbox.png](/resources/googleassistant/toolsbox.png)

# Installation

Execute `npm run install:EXT-Website` in the MMM-GoogleAssistant's folder.
```sh
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run install:EXT-Website
```

# Configuration

> Define your MMM-GoogleAssistant website configuration
{.is-info}

```js
{
  module: "MMM-GoogleAssistant/EXTs/EXT-Website",
  config: {
    debug: false,
    username: "admin",
    password: "admin",
    useAPIDocs: false
  }
},
```

> Notes:
>  ** It's an example
>  ** For better security, best way don't use default username and password
{.is-info}


> | Option  | Description | Type | Default |
> | ------- | --- | --- | --- |
> | debug | enable or not debug mode | Boolean | false
> | username | Define your username for login | String | admin
> | password | Define your password for login | String | admin
> | useAPIDocs | Display API Docs link in website  | false

## How Can I connect to MMM-GoogleAssistant website ?

MMM-GoogleAssistant website can be open with your browser
You have to know your ip address of your pi !
Sample:
 * If ip address of your pi is `192.168.0.200`

Open your browser with this address: `http://192.168.0.200:8081`
Your browser will open MMM-GoogleAssistant website :)
Now, just enter your credentials defined in website config ;)

> MMM-GoogleAssistant will inform you in logs of MagicMirror²
>```sh
>[LOG] [WEBSITE] Start listening on port 8081
>[LOG] [WEBSITE] Available locally at http://192.168.0.200:8081
>[LOG] [WEBSITE] Website Ready!
>```

> With Internet, you can use it in remote too
>
> Just map your prefered incoming port to MMM-GoogleAssistant port (8081) of your pi !
> In this case, you can control MMM-GoogleAssistant over the world with another internet connexion, or with your phone wherever you are
{.is-info}

# Docs and Testing API
`EXT-Website` have now his proper API.
You can consult API docs by enable `useAPIDocs: true` in your configuration.
You will discover `API Docs` in `MMM-GoogleAssistant` website navbar

> Note:
> This feature is only for testing and developing.
{.is-info}


# EXT-TelegramBot Commands

## /sysinfo
 - description: show system informations of your system
 - arguments: none | show | hide
 - exemples:
```
/sysinfo: Sends a summary of the state of your system in Telegram
/sysinfo show: Will display state of your system in MagicMirror²
/sysinfo hide: Will close sysinfo windows of MagicMirror²
```

# Update
```
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run update
```
