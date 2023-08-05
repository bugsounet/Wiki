---
title: EXT-Internet
description: 
published: true
date: 2023-08-05T09:38:06.342Z
tags: 
editor: markdown
dateCreated: 2022-03-05T11:00:09.615Z
---

EXT-Internet

This module allow check your internet connexion, display ping.
It can inform if connexion is lost.

> This module is an Extented plugins for `MMM-GoogleAssistant`
{.is-info}

> In addition, you can use EXT-Alert plugin, for display some information or error on your screen (Optional)
{.is-warning}

# Installation

Clone the module into your MagicMirror module folder and execute `npm intall` in the module's directory.
```sh
cd ~/MagicMirror/modules
git clone https://github.com/bugsounet/EXT-Internet
cd EXT-Internet
npm install
```

# Configuration
> To display the module insert it in the config.js file.
{.is-info}


```js
{
  module: 'EXT-Internet',
  position: 'top_left',
  config: {
    debug: false,
    displayPing: true,
    delay: 30 * 1000,
    scan: "google.fr",
    showAlert: true,
    needRestart: false
  }
},
```

## Details
> |field  | description | type | default value
> |---|---|---|---
> | debug | Enable or not debug mode | BOOLEAN | false |
> |displayPing | Display the ping value on the screen | BOOLEAN | true
> |delay | Set the interval for internet checking | NUMBER | 2* 60 * 1000
> |scan | Ping point name or address | STRING | google.fr
> |showAlert | Show or not the Alert about internet connection lost (`EXT-Alert` needed) | BOOLEAN | true
> |needRestart | Restart your MagicMirror | BOOLEAN | false

# Developer Notes

This module broadcasts:
  * `EXT_INTERNET-UP` notification when your internet connexion is available again 
  * `EXT_INTERNET-DOWN` notification when you lost your internet connexion

> With this dual notification, you can make a pause of your module and revive it 
{.is-success}


# Update
```sh
cd ~/MagicMirror/modules/EXT-Internet
npm run update
```
