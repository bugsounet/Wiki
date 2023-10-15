---
title: EXT-Bard
description: 
published: true
date: 2023-10-15T08:53:40.040Z
tags: 
editor: markdown
dateCreated: 2023-07-29T11:09:55.708Z
---

EXT-Bard is a plugin for using Google Bard

> This module need:
> `COOKIE_KEY` of your Google Bard
> `EXT-Alert` for displaying any errors
{.is-warning}
---

> For the moment, I can no longer keep a token active for more than 24 hours 😕
> I’m looking for a way around this
{.is-danger}

# How Get my personal `COOKIE_KEY`

## Step 1
Visit https://bard.google.com/ (opens in a new tab), and sign into your Google account.

## Step 2
Open the Web Inspector, and go to the Application tab.
![devtool.png](/resources/bard/devtool.png)

## Step 3
Spin open the Cookies dropdown, and click the option with https://bard.google.com.
![cookies1.png](/resources/bard/cookies1.png)

## Step 4
Look for the Cookie labeled `__Secure-1PSID` exactly
![cookies2.png](/resources/bard/cookies2.png)

## Step 5
Copy the Cookie.

![cookies3.png](/resources/bard/cookies3.png)

## Install `EXT-Bard`

Clone the `EXT-Bard` github repo and go to beta branch:

```
cd ~/MagicMirror/modules
git clone https://github.com/bugsounet/EXT-Bard
cd EXT-Bard
npm install
```

## EXT-Bard configuration

```
{
  module: 'EXT-Bard',
  config: {
    COOKIE_KEY: "Past your personal Bard Cookie there",
    scrollActivate: true,
    scrollStep: 25,
    scrollInterval: 1000,
    scrollStart: 10000
  }
},
```

> | Option  | Description | Type | Default |
> | ------- | --- | --- | --- |
> | debug | Enable or not debug mode | Boolean | false |
> | COOKIE_KEY | Your personal Bard Cookie | String | null |
> | scrollActivate | Activate or not auto-scrolling | Boolean | true |
> | scrollStep | Scrolling step in px for scrolling down| Number | 25 |
> | scrollInterval | Scrolling interval for next scrollStep | Number | 1000 |
> | scrollStart | Delay before scrolling down in ms (default: 10secs) | Number | 10000 |

## MMM-GoogleAssistant recipe

MMM-GoogleAssistant need a recipe for listen `Bard`

*  Like some other plugin, add this on `recipes:[]` feature of `MMM-GoogleAssistant` configuration
```
        recipes: [
          "../../EXT-Bard/recipe/EXT-Bard.js"
        ]
```

* If you have some other recipes: just add it next

sample:
```
        recipes: [
          "../../EXT-YouTube/recipe/EXT-YouTube.js",
          "../../EXT-FreeboxTV/recipe/EXT-FreeboxTV.js",
          "../../EXT-RadioPlayer/recipe/EXT-RadioPlayer.fr.js",
          "../../EXT-Bard/recipe/EXT-Bard.js"
        ]
```

## Commands:

### Enter in Bard Mode
Enable Jarvis and say `Bard`
Bard interface will appear

![bard.png](/resources/bard/bard.png)

### How to ask something to Bard
If you are in bard mode
Just activate `MMM-GoogleAssistant` with you prefered keyword (`Jarvis` for example) and ask your question !
`MMM-GoogleAssistant` will send your question to `EXT-Bard`

### How to disable bard mode
Just use the `stop` command :)
or `Jarvis... bard stop` for stop `EXT-Bard` only

### What about EXT-TelegramBot ?
`/bard` command is coded too !

Syntax of this command is `/bard <your question>`
`EXT-Bard` will send the response to EXT-TelegramBot and will not display it on the screen !

## Update

If an update is available, you can use this command:

```sh
cd ~/MagicMirror/modules/EXT-Bard
npm run update
```