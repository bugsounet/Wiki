---
title: Tools
description: 
published: true
date: 2024-09-07T11:30:21.954Z
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

### Note:
> This Step is not needed if you use [EXT-Updates](/EXT-Updates) plugin.
> This plugin will automaticaly update MMM-GoogleAssistant if needed
{.is-success}

## Refresh / Major Updating

> This new command allow force reinstall or update all `MMM-GoogleAssistant` components:
> `MMM-GoogleAssistant`and all `EXTs` installed
> This command make automatic things !
{.is-info}

> This command can be used when a new MagicMirror² version is installed
> When you have too many `MMM-GoogleAssistant` components to update
> When you want to refresh (like a first install) all `MMM-GoogleAssistant` components
{.is-success}

```sh
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run refresh
```

Sample of output:
```sh
~/MagicMirror/modules/MMM-GoogleAssistant$ npm run refresh

> MMM-GoogleAssistant@5.4.2 refresh
> node installer/refresh.js

Start Refreshing and Updating MMM-GoogleAssistant, Gateway and EXTs

❤ Found: EXT-Alert
✅ Update of EXT-Alert: Version: 1.3.0 (231001)
---
❤ Found: EXT-Background
✅ Update of EXT-Background: Version: 1.2.4 (231001)
---
❤ Found: EXT-Bard
✅ Update of EXT-Bard: Version: 1.1.0 (230825)
---
❤ Found: EXT-Bring
✅ Update of EXT-Bring: Version: 1.2.3 (231001)
---
❤ Found: EXT-Browser
✅ Update of EXT-Browser: Version: 1.2.3 (231001)
---
❤ Found: EXT-Detector
⠧ Updating: EXT-Detector...
<...>
---
✋ Skipped: MMM-Test
---

✌ Result:
➤ Updated: xx/xx
➤ Failed: xx/xx
➤ Skipped: xx/xx
```
