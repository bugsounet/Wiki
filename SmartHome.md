---
title: SmartHome
description: 
published: true
date: 2023-08-04T12:38:12.300Z
tags: 
editor: markdown
dateCreated: 2023-08-04T12:38:05.250Z
---

# **SmartHome Installation**

I think do you know the Google Home app of your smartphone
It is used to control the connected devices
We are therefore going to create the extension in order to control Jatvis from this application!
Naturally... when done, you can therefore control it by voice from another device that uses the google assistant :)

## Process
SmartHome needs to receive and send data
Send data it's not a problem ;)
Receive data in live from google Server in live get a little more complex
And again... it's use https protocal
So I tried to simplify as much as possible (as usual) the installation

## PreRequire

* Domaine name  or DynDNS (or equivalentq) account
* a Router
* an Google Account: same like `MMM-GoogleAssistant`, Google Home app, SmartPhone account

## Screenshot
### Google Home `Jarvis` icon:
![jarvis.png](/resources/smarthome/jarvis.png)

### On the App:
![de922e18-9655-444c-a511-74de2ec33c47-image.png](/assets/uploads/files/1678829576608-de922e18-9655-444c-a511-74de2ec33c47-image.png) 

![3780007a-8966-444c-a7e3-c7f1abeb9d62-image.png](/assets/uploads/files/1678829647983-3780007a-8966-444c-a7e3-c7f1abeb9d62-image.png) 

![768a728d-dd06-441b-a987-cc0bf07e9073-image.png](/assets/uploads/files/1678829697289-768a728d-dd06-441b-a987-cc0bf07e9073-image.png) 

![dc1389db-e7df-4f86-a4f4-1c2092b31099-image.png](/assets/uploads/files/1678829738439-dc1389db-e7df-4f86-a4f4-1c2092b31099-image.png) 

## What can this plugin do?

It's able to control plugin :)

* `EXT-Screen`: for Force turn on/off screen
* `EXT-Volume`: for volume and mute/unMute control
* `EXT-Spotify`: Play/previous/next/pause
* `EXT-CanvasLyrics`: Force (or not) full screen lyrics
* `EXT-FreeboxTV`: display FreeboxTV and control it with CH +/-
* `EXT-Pages`: change the page with source
* Naturally ... `stop` command is available too !

(... More features will be added (again) soon!)