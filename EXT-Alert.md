---
title: EXT-Alert
description: 
published: true
date: 2023-06-15T19:59:45.292Z
tags: 
editor: markdown
dateCreated: 2022-02-26T22:31:53.074Z
---

EXT-Alert is a plugins for displaying any warning, information or error on your screen

> This module an Extented of all `EXT modules`
> It's really conseilled to install it !
{.is-warning}

## Screenshot

Information sample:
![](https://raw.githubusercontent.com/bugsounet/EXT-Alert/dev/informationShot.png)

Warning sample:
![](https://raw.githubusercontent.com/bugsounet/EXT-Alert/dev/warningShot.png)

Error sample:
![](https://raw.githubusercontent.com/bugsounet/EXT-Alert/dev/errorShot.png)

# Installation
Clone the module into your MagicMirror module folder and execute `npm intall` in the module's directory.
```
cd ~/MagicMirror/modules
git clone https://github.com/bugsounet/EXT-Alert
cd EXT-Alert
npm install
```

# Configuration
> insert your configuration in the config.js file of MagicMirror.
{.is-info}


```js
{
  module: 'EXT-Alert',
  config: {
    debug: false,
    ignore: []
  }
},
```

> | Option  | Description | Type | Default |
> | ------- | --- | --- | --- |
> | debug | enable or not debug mode | Boolean | false |
> | ignore | Name of modules to displaying anything | Array of String | [] |

> This module is designed to replace the default alert module !
{.is-success}

# Developer Notes

- This module receive:
  * `EXT_ALERT`: for controling any messages to send on the screen
  
## Payload of `EXT_ALERT`
 * `type`: type of alert, it can be `notification`, `warning` or `error`
 * `message`: message to send
 * `timer`: display time on the screen in ms (5000 ms by default) [Optional]
 * `sender`: name of the sender (by default the module name sender) [Optional]
 * `icon`: the path of your personal icon [Optional]
 * `sound`: the path of your personal sound [Optional]

### `icon` and `sound` path

> The path must be from the `modules` directory of MagicMirror
> Sample: `modules/EXT-Alert/resources/information.gif`
{.is-warning}


## Sample of using:
```js
this.sendNotification("EXT_ALERT", {
  type: "information",
  message: "this a sample of notification displayer",
  sender: "@bugsounet"
})
```

It will display with animation in/out:
![](https://raw.githubusercontent.com/bugsounet/EXT-Alert/dev/informationShot.png)

## How can i have no sound with an notification ?

Just use add `sound: "none"` in your EXT_ALERT notification

sample:
```js
this.sendNotification("EXT_ALERT", {
  type: "information",
  message: "this a sample of notification displayer",
  sender: "@bugsounet",
  sound: "none"
})
```

# Update
```
cd ~/MagicMirror/modules/EXT-Alert
npm run update
```
