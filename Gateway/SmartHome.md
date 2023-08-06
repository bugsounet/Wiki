---
title: SmartHome
description: 
published: true
date: 2023-08-06T12:55:31.779Z
tags: 
editor: markdown
dateCreated: 2023-08-04T12:38:05.250Z
---

I think do you know the Google Home app of your smartphone
It is used to control the connected devices
We are therefore going to create the extension in order to control Jatvis from this application!
Naturally... when done, you can therefore control it by voice from another device that uses the google assistant :)

# Process
SmartHome needs to receive and send data
Send data it's not a problem ;)
Receive data in live from google Server in live get a little more complex
And again... it's use https protocal
So I tried to simplify as much as possible (as usual) the installation

# PreRequire

* Domaine name  or DynDNS (or equivalent) account
* a Router
* an Google Account: same like `MMM-GoogleAssistant`, Google Home app, SmartPhone account

# Screenshot
## Google Home `Jarvis` icon:
![jarvis.png](/resources/smarthome/jarvis.png)

## On the App:
![app1.png](/resources/smarthome/app1.png)

![app2.png](/resources/smarthome/app2.png)

![app3.png](/resources/smarthome/app3.png)

![app4.png](/resources/smarthome/app4.png)

# What can this plugin do?

It's able to control plugin :)

* `EXT-Screen`: for Force turn on/off screen
* `EXT-Volume`: for volume and mute/unMute control
* `EXT-Spotify`: Play/previous/next/pause
* `EXT-CanvasLyrics`: Force (or not) full screen lyrics
* `EXT-FreeboxTV`: display FreeboxTV and control it with CH +/-
* `EXT-Pages`: change the page with source
* Naturally ... `stop` command is available too !

(... More features will be added (again) soon!)

---

# SmartHome guide:

1. [Installation](/Gateway/SmartHome/Installation)
2. [Create a Google Action Project](/Gateway/SmartHome/ActionNewProject)
3. [Configure: Google Action](/Gateway/SmartHome/SmartHomeActions)
4. [Configure: your CLIENT_ID](/Gateway/SmartHome/CLIENT_ID)
5. [Configure: HomeGraph](/Gateway/SmartHome/HomeGraph)
6. [DownLoad credentials]()
7. [configure Webserver]()
8. [First Start of MagicMirror with Gateway and SmartHome functionality]()
9. [Link with Google Home]()
10. [Finalize device registration]()