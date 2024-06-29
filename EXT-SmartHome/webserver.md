---
title: 7. Configure Webserver
description: 
published: true
date: 2024-06-29T12:18:45.238Z
tags: 
editor: markdown
dateCreated: 2024-01-02T12:31:06.547Z
---

# Let's configure the webserver for `https` using

> **Require Warning:**
> *You have already configured and authorized your router in order to communicate from the internet on ports `80` and `443`*
>  *MagicMirror² is **NOT** launched*
>  For this sample I use `demo.bugsounet.fr` as sub-domaine name !
{.is-warning}


Try this prepared command:
```sh
cd ~/MagicMirror/modules/EXT-SmartHome
npm run smarthome
```

* `[SMARTHOME]~What is your domain name?~`
enter your sub-domaine name sample: `demo.bugsounet.fr`

* The prepared command will auto configure `nginx`

![nginx2.png](/resources/smarthome/nginx2.png)

* `[SMARTHOME] Router is ready ? [Y/n] `
By respond `Y`: you have prepared your router and installation will continue and install `https` certificate

![nginx3.png](/resources/smarthome/nginx3.png)

> **Notes:**
>  Maybe It can ask you for information to fill in (registration to cerbot)
>  If failed prepared program will inform you, in RED with the reason above !
{.is-warning}

![nginx4.png](/resources/smarthome/nginx4.png)