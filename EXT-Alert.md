---
title: EXT-Alert
description: 
published: true
date: 2024-03-22T23:37:27.831Z
tags: 
editor: markdown
dateCreated: 2022-02-26T22:31:53.074Z
---

EXT-Alert is a plugins for displaying any warning, information or error on your screen

> This module an Extented of all `EXT modules`
> It's really conseilled to install it !
{.is-warning}

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
    style: 1,
    ignore: []
  }
},
```

> | Option  | Description | Type | Default |
> | ------- | --- | --- | --- |
> | debug | enable or not debug mode | Boolean | false |
> | style | displayer style | Number | 1 |
> | ignore | Name of modules to displaying anything | Array of String | [] |

> This module is designed to replace the default alert module !
{.is-success}


# style screenshot

## style: 0 (v1.x style)

Information sample:
![](https://raw.githubusercontent.com/bugsounet/EXT-Alert/dev/screenshot/informationShot.png)

Warning sample:
![](https://raw.githubusercontent.com/bugsounet/EXT-Alert/dev/screenshot/warningShot.png)

Error sample:
![](https://raw.githubusercontent.com/bugsounet/EXT-Alert/dev/screenshot/errorShot.png)

## style: 1 (sweetalert2 style)
Information sample:
![](https://raw.githubusercontent.com/bugsounet/EXT-Alert/dev/screenshot/InfoStyle1.png)

Warning sample:
![](https://raw.githubusercontent.com/bugsounet/EXT-Alert/dev/screenshot/WarnStyle1.png)

Error sample:
![](https://raw.githubusercontent.com/bugsounet/EXT-Alert/dev/screenshot/ErrorStyle1.png)
## style: 2 (alertify style)

![](https://raw.githubusercontent.com/bugsounet/EXT-Alert/dev/screenshot/style3.png)


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
