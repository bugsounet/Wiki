---
title: EXT-Touch
description: 
published: true
date: 2024-12-31T01:09:35.262Z
tags: 
editor: markdown
dateCreated: 2024-03-22T22:58:07.940Z
---

# Welcome to the EXT-Touch wiki!

> Activate `MMM-GoogleAssistant` with a Touch Screen by Touching the Google Icon
{.is-info}

# Installation

> I have created automatic installer for RaspberryPi and Linux Debian machines.
> Auto install script will propose to install needed dependencies.
{.is-info}

> For OSX machines, auto install script is not yet implented.
> So, manuel installation is nedeed and no help will be given for this
{.is-warning}

## Auto install (for RaspberryPi or Debian Linux machines only)
```sh
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run install:EXT-Touch
```
 * No other `npm` commands (e.g. npm audit fix) are needed after installation (they can break package dependencies)!

# EXT-Touch Configuration

> use config.js file of MagicMirror for configuring EXT-Touch
{.is-info}


```js
{
  module: "MMM-GoogleAssistant/EXTs/EXT-Touch",
  position: "top_left"
},
```

# Update
> If a new version of EXT-Touch is available
{.is-info}

```sh
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run update
```

# Uninstall
```sh
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run remove:EXT-Touch
```
