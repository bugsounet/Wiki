---
title: EXT-RadioPlayer
description: 
published: true
date: 2024-05-18T13:03:15.287Z
tags: 
editor: markdown
dateCreated: 2022-03-05T11:08:09.889Z
---

EXT-RadioPlayer is a module for the [MagicMirror](https://github.com/MichMich/MagicMirror) project by [Michael Teeuw](https://github.com/MichMich).

This allows to play radio station on MagicMirror

> This module is an Extented plugins for `MMM-GoogleAssistant`
{.is-info}

> This module need `EXT-VLCServer` for working
{.is-warning}

# Installation
Clone the module into your MagicMirror module folder and execute `npm intall` in the module's directory.
```
cd ~/MagicMirror/modules
git clone https://github.com/bugsounet/EXT-RadioPlayer
cd EXT-RadioPlayer
npm install
```

# Configuration
> To display the module insert it in the config.js file.
{.is-info}


```js
{
  module: 'EXT-RadioPlayer',
  position: 'top_right',
  animateIn: "flipInX",
  animateOut: "flipOutX",
  config: {
    debug: false,
    minVolume: 30,
    maxVolume: 75,
  }
},
```

<br>

## Configuration options

> Description of config feature
{.is-info}


| Option           | Description | Type | default
|----------------- |----------- |---|---
| `debug`          | *Optional* Enable Log level | Boolean | false
| minVolume | Volume to set when assistant speaking (in %) | Number | 30
| maxVolume | Volume to set when radio playing (in %) | Number | 75
<br>



# French Radio
<br>
## Un total de 15 radios ont été pré-configurés

- [Chérie FM](https://www.cheriefm.fr/)
- [RTL](https://www.rtl.fr/)
- [Rire Et Chansons](https://www.rireetchansons.fr/)
- [France Info](https://www.francetvinfo.fr/)
- [RTL2](https://www.6play.fr/rtl2)
- [Fun Radio](https://www.funradio.fr/)
- [Europe 1](https://www.europe1.fr/)
- [RFM](http://www.rfm.fr/)
- [RMC](https://rmc.bfmtv.com/)
- [NRJ](https://www.nrj.fr/)
- [Nostalgie](https://www.nostalgie.fr/)
- [Contact FM](https://www.mycontact.fr/)
- [Voltage](https://www.voltage.fr/)
- [Skyrock](https://skyrock.fm/)
- [Radio FG](https://www.radiofg.com/)

## Configuration

Afin de simplifier la configuration au maximum, un `recipe` a été créé.<br>
Il suffit simplement de l'ajouter à la configuration de `GoogleAssistant`<br>
Ce `recipe` se nomme: `EXT-RadioPlayer.fr.js`<br>
Pour l'ajouter, editer la configuration de `MMM-GoogleAssistant` dans votre fichier config.js<br>
exemple:
```js
{
  module: "MMM-GoogleAssistant",
  ...
  config: {
    ...
    recipes: [
      "../../EXT-RadioPlayer/recipe/EXT-RadioPlayer.fr.js",
    ]
    ...
```
Dans le cas où vous avez déjà d'autres `recipes`:<br>
exemple:
```js
{
  module: "MMM-GoogleAssistant",
  ...
  config: {
    ...
    recipes: [ 
      "../../EXT-RadioPlayer/recipe/EXT-RadioPlayer.fr.js",
      "Un_autre_recipe.js"
    ]
    ...
```
## Activation par commande vocale

Une fois le `recipe` installé, il faudra bien sur redémarrer `MagicMirror`<br>
Activez votre assistant avec votre `keyword` préféré et dites par exemple:<br>
`Mets Chérie FM`<br>
L'assistant envoie les données nécessaires et se connectera à la radio demandé.<br>

------
# Create your own radio recipe for your country
<br>

## Prepare

for create a radiolink for MMM-GoogleAssistant you need 2 things:

- the streaming link
- the logo of the radio station

you can understand that i can't do it for all countries ...<br>
I do it for my country (France)<br>
then let you search with your favorite search engine

## I found the streaming link and the logo ! What can i do now ?

You have to create your own recipe !, I will help you to create it...<br>

GoogleAssistant have a very good functionality... search what you have said and do something<br>
We will use this function.<br>

*sample with one radio station (French radio `Chérie FM`)*<br>

Don't worry, i will explain

```js
var recipe = {
  transcriptionHooks: {
    "cheriefm": {
      pattern: "mets chérie fm",
      command: "cheriefm"
    },

  },

  commands: {
    "cheriefm": {
      notificationExec: {
        notification: "EXT_RADIO-START",
        payload: (params) => {
          return {
            img: "modules/EXT-RadioPlayer/Logos/FR/ChérieFM.png",
            link: "https://scdn.nrjaudio.fm/fr/30201/mp3_128.mp3?origine=EXT-RadioPlayer&cdn_path=audio_lbs9"
          }
        }
      },
      displayResponse: false,
      soundExec: {
        chime: "open"
      }
  }
}
exports.recipe = recipe
```

*Explain*

you can see 2 blocks in recipe:
 - `transcriptionHooks` : it's the vocal search block
 - `commands` : command to execute

### transcriptionHooks explain line by line

 - `"cheriefm": {` : identification name of the search, there i named this search `cheriefm` (the name of the radio station)
 - `pattern: "mets chérie fm",` : pattern feature is the EXACT vocal search for execute a command<br>
there it's means : `jarvis, mets chérie fm`
 - `command: "cheriefm"` : name of the command to execute in the `commands block`<br>
there for simply and more visibility, i named my command `cheriefm`

so ... not complex !

### commands

lets continue avec commands block <br>
there is very easy !

 - `"cheriefm": {` : just report the command name that you have defined in transcriptionHooks

 - hum ... you said to me ... i have the streaming link and the logo ...<br>
 this is the place to paste it !

   - img: "your logo link"
   - link: "your streaming link"

### Got it ! and now ?

 * Save your file as `EXT-RadioPlayer.js` in `~/MagicMirror/modules/EXT-RadioPlayer/recipes` directory <br>
 * add your recipe to GoogleAssistant configuration
```js
recipes: [
  "../../EXT-RadioPlayer/recipe/EXT-RadioPlayer.js"
],
```
if you have already a recipes configuration just add it
```js
recipes: [
  "my_prefered_recipes.js",
  "../../EXT-RadioPlayer/recipe/EXT-RadioPlayer.js"
],
```
and restart your mirror !

### Call the radio

 * just call your assistant and say your defined vocal search
 * The logo will display and radio playing

### Multi-Radio recipe
 * look my prepared recipes for [french radio](https://github.com/bugsounet/EXT-RadioPlayer/blob/dev/recipe/EXT-RadioPlayer.fr.js)
 
# Italian Radio

Prepared recipes for Italian users, you can use `EXT-RadioPlayer.it.js` recipe
This recipe have 9 pre-configured radio
  * Radio kiss kiss
  * Radio 101
  * radio italia
  * Radio 1
  * Radio anni 90
  * Radio 105
  * rds
  * rtl
  * radio dj

## How call a radio Station

For sample, if you want `radio kiss kiss`
`Jarvis ... metti radio kiss kiss`

# Update

```
cd ~/MagicMirror/modules/EXT-RadioPlayer
npm run update
```