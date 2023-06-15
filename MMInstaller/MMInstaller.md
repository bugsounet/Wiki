---
title: Auto-Installer for new install of MagicMirror
description: 
published: true
date: 2023-05-08T13:04:03.156Z
tags: 
editor: markdown
dateCreated: 2022-08-13T11:21:10.072Z
---

# MagicMirror installer with MMM-GoogleAssistant Suite (optional)

## Pre-require:
 * Raspberry pi 3 and more
 * `Raspberry Pi OS 32-bit with desktop` from `raspberrypi.com` website [there](https://www.raspberrypi.com/software/operating-systems/#raspberry-pi-os-32-bit)
 * Fresh install with update done
 
## What this script can do?

 * Scan All needed dependencies for MagicMirror using (node / npm for exemple)
 * Fetch and install Last MagicMirror version
 * Install pm2 app and link MagicMirror on it (optional)
 * disable screen saver (optional)
 * install MagicMirror splashscreen (optional)
 * install default `config.js` file
 * install default GoogleAssistant suite (optional)
 * install default `config.js` file with GoogleAssistant Suite
 * update properly MagicMirror
 * update properly GoogleAssistant Suite
 
## Installing:
 * `curl` and `git` tools
 ```
 sudo apt-get install curl git -y
 ```
 * Cloning and installing this repository
 ```
 cd ~
 git clone https://github.com/bugsounet/installer
 cd installer
 ./install
 ```
 * Pre-Installing the MMM-GoogleAssistant suite
 
 After install MagicMirror, installer will ask to you:
 ```sh
 Do you want to preinstall MMM-GoogleAssistant? [Y/n] 
 Your choice:
```
by responding `Y`, it will install:
 * MMM-GoogleAssistant
 * Gateway
 * EXT-Detector
 * EXT-Alert
 * New default `config.js` file

## Updating Magicmirror and @bugsounet electron based modules

When an update of MagicMirror is available, you can use this tool:
```
cd ~/installer
npm run update
```
Installer will do an proper update of MagicMirror and will scan if some @bugsounet modules need to be reinstalled in accord with new electron version

# Thanks
[@sdetweil](https://github.com/sdetweil/MagicMirror_scripts): MagicMirror installer/updater tools