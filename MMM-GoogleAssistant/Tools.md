---
title: Tools
description: 
published: true
date: 2024-12-31T00:33:08.395Z
tags: 
editor: markdown
dateCreated: 2022-03-14T17:58:57.904Z
---

# Magical Commands of MMM-GoogleAssistant
<br>

## Tokens Generator

> This commands allow to create/reinstall any needed tokens for MMM-GoogleAssistant
{.is-info}

> This command works only on terminal of the desktop of your raspberry Pi 
{.is-warning}


```sh
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run token
```

<br>

## Register MMM-GoogleAssistant to `GoogleHome App`

> This command will register MMM-GoogleAssistant like a device
{.is-info}


```sh
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run register
```

> In your google Home App, you will have a new device named: `Jarvis`.
{.is-success}

> When you device is registred, you have to enable `deviceRegistred: true,` in your [config](https://wiki.bugsounet.fr/en/MMM-GoogleAssistant/Configuration#field-assistantconfig)
{.is-success}


## How to enable personal search ?

Activate your assistant with your favorite keyword and ask him to show photos or add an appointment

GoogleServer will ask to you to enable `personal result` and will send a popup in your phone.

Now, you have to complete the name of the device `Jarvis` and check personal result !

## Delete MMM-GoogleAssistant to `GoogleHome App`

> This command will delete `Jarvis` device from GoogleHome App
{.is-info}


```sh
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run delete
```

## List of registred project

```sh
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run list
```

## Update of MMM-GoogleAssistant
> If a new version of GoogleAssistant is available
{.is-info}

```sh
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run update
```

### Notes:

> MMM-GoogleAssistant is able to detect installed plugin and will update it automaticaly if needed
{.is-success}

> This Step is not needed if you use [EXT-Updates](/EXT-Updates) plugin.
> This plugin will automaticaly update MMM-GoogleAssistant if needed
{.is-success}
