---
title: SmartHome
description: 
published: true
date: 2023-08-06T10:23:16.987Z
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

* Domaine name  or DynDNS (or equivalent) account
* a Router
* an Google Account: same like `MMM-GoogleAssistant`, Google Home app, SmartPhone account

## Screenshot
### Google Home `Jarvis` icon:
![jarvis.png](/resources/smarthome/jarvis.png)

### On the App:
![app1.png](/resources/smarthome/app1.png)

![app2.png](/resources/smarthome/app2.png)

![app3.png](/resources/smarthome/app3.png)

![app4.png](/resources/smarthome/app4.png)

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

---

## Installation

### Project_id
You know to remember what is you `project_id` used when you create `credentials.json` file of MMM-GoogleAssistant

I create a command line for discover it ! (so don't have to search ahahah !)
try this in a Terminal:
```
cd ~/MagicMirror/modules/Gateway
npm run project
```
result will be something like this:
```
~/MagicMirror/modules/Gateway$ npm run project

> Gateway@3.X.X project
> installer/check_ProjectID.sh

Your MMM-GoogleAssistant project_id is: XXXXXXXXX
---
Your SmartHome project_id is: credentials not found!
```

**Open a note pad and past your MMM-GoogleAssistant project_id!**

Note: Don't worry about `credentials not found` for SmartHome, we will create it later!

## It's time to change default `username` and `password` of `Gateway` configuration
why ?
You will have access from internet to `Gateway` so, for security, it's better to don't use default `username` and `password`
[This part](https://wiki.bugsounet.fr/en/Gateway#configuration) will help and replace it by your own !

## Domaine name with fixed WAN ip address or DynDNS

# What's IP WAN /IP LAN ?
`IP WAN` is your ip from Internet
`IP LAN` is your device ip from your local network (inside your home)

# What's a domain name and a sub-domain ?

a domaine sample it's like `bugsounet.fr`
a sub-domain it's like `forum.bugsounet.fr` (`forum` is the sub-domain)

--> If you have a domaine name and an fixed WAN ip address:
create a sub-domaine and redirect it to your WAN ip

--> if you have a dyndns domain name, verify if really redirect to your WAN adress
# External connect port (from internet)
SmartHome need 2 ports:
 * `80`: for create http server and initialize https protocol
 * `443`: for using https protocol with SmartHome and Google SmartHome

**Enter inside your router setting and redirect this 2 ports to your raspberry pi LAN ip address**

# My Sample value used in this wiki

sub-domaine name: `demo.bugsounet.fr`

# When routing done, check if this is configured correctly

Open the webpage with your `sub-domaine` name (or dyn-dns)
sample: `http://demo.bugsounet.fr` (replace `demo.bugsounet.fr` by yours)

**If works: You must have the `nginx` default page**

![nginx.png](/resources/smarthome/nginx.png)


---

Google Actions
Let's configure google actions!

# Connect to [Google Action Console](https://console.actions.google.com/)

# Create a new Project
![action1.png](/resources/smarthome/action1.png)

## Name it `MMM-GoogleAssisant` (and make it in accord with your language and country)
![action2.png](/resources/smarthome/action2.png)

**/!\ it must be the same project name like when you create your credentials for `MMM-GoogleAssistant` [there](https://wiki.bugsounet.fr/MMM-GoogleAssistant/SetupCredentials)**
**Google can purpose a choice, let's check it!**

... and `Create project` or `Import project`

# Select `Smart Home` 
![sh1.png](/resources/smarthome/sh1.png)
... and click `start Building`

![sh2.png](/resources/smarthome/sh2.png)

---

# Close your brower and reconnect to [google actions](https://console.actions.google.com/)
## Select your project
## Select 3 dots on the top right
![action3.png](/resources/smarthome/action3.png)

## `Select Project setting`
![action4.png](/resources/smarthome/action4.png)

![action5.png](/resources/smarthome/action5.png)

**It's must match with `npm run project` result (copied in note pad)**

---

