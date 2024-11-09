---
title: EXT-Spotify
description: 
published: true
date: 2024-11-09T10:40:00.734Z
tags: 
editor: markdown
dateCreated: 2022-03-11T22:45:57.282Z
---

This module show current playback of any devices

> This module is an Extented plugins for `MMM-GoogleAssistant`
{.is-info}

> In addition, you can use some plugins:
> `EXT-Librespot` for playing spotify music on your mirror with a Premium account (optional)
> `EXT-TelegramBot` for controling music with the bot (optional)
{.is-warning}

# Installation
Clone the module into your MagicMirror module folder and execute `npm intall` in the module's directory.
```
cd ~/MagicMirror/modules
git clone https://github.com/bugsounet/EXT-Spotify
cd EXT-Spotify
npm install
```

# Configuration
> To display the module insert it in the config.js file.
{.is-info}


```js
{
  module: 'EXT-Spotify',
  position: 'top_left',
  animateIn: "flipInX",
  animateOut: "flipOutX",
  config: {
    updateInterval: 1000,
    idleInterval: 10000,
    useBottomBar: false,
    CLIENT_ID: "",
    CLIENT_SECRET: "",
    mini: true,
    forceSCL: false,
    noCanvas: false
  }
},
```

|field  | description | type | default value
|---|---|---|---
|updateInterval | Update interval when playing (refresh) | NUMBER | 1000
|idleInterval | Update interval when idle (check if Spotify active) | NUMBER | 10000
|useBottomBar | Activate visual of the current playback in the bottom bar | BOOLEAN | false
|CLIENT_ID | Client ID of your Spotify account | STRING | ""
|CLIENT_SECRET | Client Secret of your Spotify account | STRING | ""
|mini | Activate `mini` style instead of `big` style | BOOLEAN | true
|forceSCL | Force displaying Canvas and Lyrics on all devices | BOOLEAN | false 
|noCanvas | Don't display Canvas with `EXT-SpotifyCanvasLyrics` displayer | BOOLEAN | false

> You can play Spotify Music To MagicMirror
> Actually 2 players are available:
> `EXT-Raspotify` or `EXT-Librespot`
{.is-warning}

> `forceSCL` and `noCanvas` can only be used with `EXT-SpotifyCanvasLyrics` plugin
{.is-danger}


# Generate Token

## Pre-installing

**Visual Spotify setup**

1. Go to https://developer.spotify.com
2. Navigate to **DASHBOARD** > **Create an app** (fill information as your thought)
3. Setup the app created, (**EDIT SETTINGS**)
   - Redirect URIs. : `http://localhost:8888/callback`
   - That's all you need. Just save it.
4. Now copy your **Client ID** and **Client Secret** to any memo
5. Past your `CLIENT_ID` and `CLIENT_SECRET` in the configuration

> Note:
> Spotify Free member can ONLY display the visual of any device that plays music
{.is-danger}

## Post-installing
<br>

### Create the token
In RPI Desktop, log in in a Terminal (you can use VNC)
```sh
cd ~/MagicMirror/modules/EXT-Spotify
npm run token
```

Then, Allowance dialog popup will be opened. You MUST LOG IN and accept connect to create a token.<br>
That's all. `tokenSpotify.json` will be created, if success.

# `MMM-GoogleAssistant` recipe for vocal control
A prepared recipe is inclued and waiting for your use
Just add it in the config of MMM-GoogleAssistant

 * sample:
```js
recipes: [
  "../../EXT-Spotify/recipe/EXT-Spotify.js"
],
```
 * if you have other recipe, just add it like this:
```js
recipes: [
  "my_recipe.js",
  "../../EXT-Spotify/recipe/EXT-Spotify.js"
],
```
## How to use it ?

activate your mirror with your prefered keyword and just say:

* `Alan Walker on Spotify`: Assistant will search some music of Alan Walker on spotify and play it
* `Alan Walker Faded on Spotify`: Assistant will search Alan Walker and the title Faded on spotify and play it
* `playlist Top Hit on Spotify`: Assistant will search the playlist Top Hit on spotify and play it
* `album K-391 on Spotify`: Assisant will search the album of K-391 and play it

You can choice your type of search in the begining of the request (artist, playlist, album, track)<br>
You can translate type of search in your language with type feature: `typeArtist`,`typePlaylist`,`typeAlbum` and `typeTrack`

  * Multi language : EN/FR/IT
  * Common commands:
    * `spotify play`: to launch spotify and play last music
    * `spotify pause`: make pause ;)
    * `spotify stop`: for stop it !
    * `spotify volume [0-100]`: for controling volume
  * EN commands:
    * `[type of search] <your request> on spotify`: make a music search on spotify and play it. type of search is optional
    * `spotify next`: next music on the playlist
    * `spotify previous`: previous music on the playlist
    * `spotify shuffle`: make shuffle playlist
    * `spotify repeat`: repeat playlist or track
    * `spotify transfer to [device name]`: transfer music to a new device 
  * FR commands:
    * `[type de recherche] <votre demande> sur spotify`: faire une recherche de musique sur spotify. Le type de recherche est optionel
    * `spotify suivante`: musique suivante
    * `spotify précédente`: musique précédente
    * `spotify aléatoire`: active la lecture aléatoire
    * `spotify répète`: active la répétition
    * `spotify transfert vers [nom de l'appareil]`: transfert la musique vers un nouveau lecteur
  * IT commands: [Need translator EN->IT]
    * `[type of search] <your request> su spotify`: make a music search on spotify and play it. type of search is optional
    * `spotify seguente`: next music on the playlist
    * `spotify precedente`: previous music on the playlist
    * `spotify casuale`: make shuffle playlist
    * `spotify ripeti`: repeat playlist or track
    * `spotify trasferisci a [device name]`: transfer music to a new device  

by editing `pattern` field in the recipe you can make the recipe for your language

## Notes
<br>

### Needed
* Spotify Premium account for playing and display the visual of any device that plays music
* Linked Spotify account with Google Home app
* Your voice !

### Spotify Free Members Restrictions

> You can ONLY display the visual of any device that plays music.
> You CAN'T play any music in the Mirror
> You CAN'T use Vocal Control or telegramBot commands
{.is-danger}


# EXT-TelegramBot Commands

`EXT-Spotify` have a telegramBot command.

Just try `/spotify`:

> `/spotify play`: Launch music (last title)
> `/spotify pause`: Pause music
> `/spotify stop`: Stop music
> `/spotify next`: Next track
> `/spotify previous`: Previous track
> `/spotify volume [0-100]`: Volume control, it need a value 0-100
> `/spotify to [device name]`: Transfert music to another device (case sensitive)
{.is-info}

# Update

```
cd ~/MagicMirror/modules/EXT-Spotify
npm run update
```
