---
title: MMM-Xbox
description: 
published: true
date: 2021-07-14T18:27:22.679Z
tags: 
editor: markdown
dateCreated: 2021-07-14T18:24:30.329Z
---

The Xbox SmartGlass For Magic Mirror

# Screenshoot
* Default Style:
![](https://raw.githubusercontent.com/bugsounet/MMM-Xbox/master/screenshoot.jpg)
* Mini Style:
![](https://raw.githubusercontent.com/bugsounet/MMM-Xbox/master/screenshoot2.jpg)

# Pre-require
 * python3.6 and more
 * pip3

> python and pip version will not be checked by installer !
{.is-danger}


# Installation

```
cd ~/Magicmirror/modules
git clone https://github.com/bugsounet/MMM-Xbox.git
cd MMM-Xbox
npm install
```

# Configuration
```
  {
    module: "MMM-Xbox",
    position: "top_center",
    config: {
		  autohide: false, // auto hide when inactive
		  mini: false, // mini display style
		  debug: false, // debug
		  ip: "", // ip adress of the xbox
		  xboxlivelogin: "", // xbox live login
		  xboxlivepassword: "" // xbox live password
    }
  },
```

# You need to reinstall this module ?
```
cd ~/Magicmirror/modules/MMM-Xbox
npm run clean
npm install
```

> Note: The clean script (`npm run clean`) will delete ALL Xbox dependencies
{.is-warning}

# Setting up the Xbox
> The plugin needs to be allowed to connect to your Xbox.
> To allow this make sure you set the setting to allow anonymous connections in Settings -> Devices -> Connections.
{.is-warning}

# Notification Sent
* XBOX_ACTIVE : the console is on-line
* XBOX_INACTIVE : the console is off-line
* XBOX_NAME : Current name Game / Application

# Notification Received
* XBOX_ON : turn on the console
* XBOX_OFF : turn off the console

# TelegramBot Commands
* /turnon : Wake up the xbox
* /turnoff : Shutdown the xbox

# Notes
* Last tested: 14/07/2021
```sh
$ pip --version
pip 21.1.3 from /home/pi/.local/lib/python3.7/site-packages/pip (python 3.7)
$ python -V
Python 3.7.3
```
* If your microsoft account use 2FA Authenticator (2FAS), this modules will not works