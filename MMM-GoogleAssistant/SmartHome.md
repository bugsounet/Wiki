---
title: SmartHome
description: 
published: true
date: 2024-01-02T12:41:27.706Z
tags: 
editor: markdown
dateCreated: 2024-01-01T13:35:22.515Z
---

I think do you know the Google Home app of your smartphone
It is used to control the connected devices
We are therefore going to create the extension in order to control Jarvis from this application!
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

1. [Installation](/MMM-GoogleAssistant/SmartHome/Installation)
2. [Create a Google Action Project](/MMM-GoogleAssistant/SmartHome/ActionNewProject)
3. [Configure: Google Action](/MMM-GoogleAssistant/SmartHome/SmartHomeActions)
4. [Configure: your CLIENT_ID](/MMM-GoogleAssistant/SmartHome/CLIENT_ID)
5. [Configure: HomeGraph](/MMM-GoogleAssistant/SmartHome/HomeGraph)
6. [DownLoad credentials](/MMM-GoogleAssistant/SmartHome/DownloadCredentials)
7. [Configure Webserver](/MMM-GoogleAssistant/SmartHome/webserver)
8. [First Start of MagicMirror with Gateway and SmartHome functionality](/MMM-GoogleAssistant/SmartHome/FirstStart)
9. [Link with Google Home](/Gateway/SmartHome/GoogleHomeLink)
10. [Finalize device registration](/Gateway/SmartHome/GoogleAssistantLink)
11. [How use it](/Gateway/SmartHome/Using)