---
title: 1. Installation
description: 
published: true
date: 2024-01-01T13:41:16.235Z
tags: 
editor: markdown
dateCreated: 2024-01-01T13:37:50.831Z
---

# Installation

## Project_id
You know to remember what is you `project_id` used when you create `credentials.json` file of MMM-GoogleAssistant

I create a command line for discover it ! (so don't have to search ahahah !)
try this in a Terminal:
```
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run project
```
result will be something like this:
```
~/MagicMirror/modules/MMM-GoogleAssistant$ npm run project

> MMM-GoogleAssistant@5.X.X project
> installer/check_ProjectID.sh

Your MMM-GoogleAssistant project_id is: XXXXXXXXX
---
Your SmartHome project_id is: credentials not found!
```

**Open a note pad and past your MMM-GoogleAssistant project_id!**

Note: Don't worry about `credentials not found` for SmartHome, we will create it later!

# It's time to change default `username` and `password` of `MMM-GoogleAssistant` website configuration
why ?
You will have access from internet to `MMM-GoogleAssistant` so, for security, it's better to don't use default `username` and `password`
[This part](https://wiki.bugsounet.fr/MMM-GoogleAssistant/Configuration#field-website) will help and replace it by your own !

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

