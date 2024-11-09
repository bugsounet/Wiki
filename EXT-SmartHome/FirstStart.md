---
title: 8. First Start of MagicMirror with MMM-GoogleAssistant and SmartHome functionality
description: 
published: true
date: 2024-11-09T11:42:16.822Z
tags: 
editor: markdown
dateCreated: 2024-01-02T12:36:15.339Z
---

# It's now time to define an `username` for `EXT-SmartHome`

This `username` will be used to associate username with google token.
You can set whatever you want as username.
BUT Once defined you can't change it (otherwise you can no longer identify yourself to the Google service).

Let's finish to configure `EXT-SmartHome` in config.js file of MagicMirror² configuration.

```js
{
  module: "EXT-SmartHome",
  config: {
    username: "myprefered_username_for_Google",
    password: "My Password defined in Google Action",
    CLIENT_ID: "My Client ID defined in Google Action"
  }
},
```

# It's time to Start `MagicMirror²`

So ... start MagicMirror and wait all is initialized !
> At this moment, Don't worry about `MMM-GoogleAssistant Alert` Error
{.is-warning}

# Verify link of `EXT-Website` and `SmartHome`
> In this wiki, I have used `demo.bugsounet.fr` domain name
{.is-info}

> Naturally change `demo.bugsounet.fr` by your own !
{.is-warning}

## Try to open `EXT-Website` with your domain name

https://demo.bugsounet.fr

![login.png](/resources/smarthome/login.png)

> You must have `EXT-Website` login page
{.is-success}

## Try to open `SmartHome` test page with ypur domain name

https://demo.bugsounet.fr/smarthome

![smarthome.png](/resources/smarthome/smarthome.png)

> You must discover `SmartHome` test page
{.is-success}


> **Yeah, You have now access to `EXT-Website` everywhere in the world !**
{.is-success}
