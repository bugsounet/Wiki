---
title: Radio_help
description: 
published: true
date: 2021-06-19T08:59:50.077Z
tags: 
editor: markdown
dateCreated: 2021-06-19T08:53:27.097Z
---

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
      functionExec: {
        exec: () => {
          this.radioCommand({
            img: "https://www.hbca07.fr/media/uploaded/sites/5499/partenaire/583038d328d24_slidercheriefm.jpg",
            link: "https://scdn.nrjaudio.fm/fr/30201/mp3_128.mp3?origine=EXT&cdn_path=audio_lbs9"
          })
        }
      },
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

 * Save your file as `ExtRadio.js` in `~/MagicMirror/modules/MMM-GoogleAssistant/recipes` directory <br>
 * add your recipe to GoogleAssistant configuration
```js
recipes: [ "ExtRadio.js"],
```
if you have already a recipes configuration just add it
```js
recipes: [ "my_prefered_recipes.js", "ExtRadio.js"],
```
and restart your mirror !

### Call the radio

 * just call your assistant and say your defined vocal search
 * The logo will display and radio playing

### Multi-Radio recipe
 * look my prepared recipes for [french radio](https://github.com/bugsounet/MMM-GoogleAssistant/blob/dev/recipes/ExtRadio_fr.js)