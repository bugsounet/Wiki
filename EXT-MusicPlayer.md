---
title: EXT-MusicPlayer
description: 
published: true
date: 2023-07-21T13:15:31.103Z
tags: 
editor: markdown
dateCreated: 2022-03-05T10:46:11.378Z
---

EXT-MusicPlayer is a module for the [MagicMirror](https://github.com/MichMich/MagicMirror) project by [Michael Teeuw](https://github.com/MichMich).

> This module will play any music found on a USB Key or in defined local directory
{.is-info}

> This module is an Extented plugins for `MMM-GoogleAssistant`
{.is-info}

> In addition, you can use `EXT-Alert` plugin, for display some information or error on your screen (Optional)
{.is-warning}

# Installation

Clone the module into your MagicMirror module folder and execute `npm intall` in the module's directory.
```
cd ~/MagicMirror/modules
git clone https://github.com/bugsounet/EXT-MusicPlayer
cd EXT-MusicPlayer
npm install
```

# Configuration
> To display the module insert it in the config.js file.
{.is-info}
```js
{
  module: 'EXT-MusicPlayer',
  position: 'top_left',
  config: {
    debug: false,
    useUSB: false,
    musicPath: "/home/pi/Music",
    checkSubDirectory: false,
    random: false,
    autoStart: false,
    minVolume: 30,
    maxVolume: 100
  }
},
```
### Details
> |field | description | type | default value
> |---|---|---|---
> |debug | Enable debug mode or not | BOOLEAN | false
> |useUSB | If you prefer play file from an USB Key, set it to `true` | BOOLEAN | false
> |musicPath | Music path for playing music from Local Files | STRING | "/home/pi/Music"
> |checkSubDirectory | Should this module inspect sub directory for create music list ? | BOOLEAN | true
> | random | Play music in random | false |
> |autoStart | AutoStart USB key Music at boot of MagicMirror or when USB key is plugged in | BOOLEAN | false
> |minVolume | Volume to set when assistant speaking | NUMBER | 30
> |maxVolume | Volume to set when music playing | NUMBER | 100

> Notes:
>
> ** Volume is in %
> ** Volume is used only with `MMM-GoogleAssistant`
{.is-info}

# recipe for `MMM-GoogleAssistant` for vocal control
A prepared recipe is inclued and waiting for your use
Just add it in the config of MMM-GoogleAssistant

 * sample:
```js
recipes: [
  "../../EXT-MusicPlayer/recipe/EXT-MusicPlayer.js",
],
```
 * if you have other recipe, just add it like this:
```js
recipes: [
  "my_recipe.js",
  "../../EXT-MusicPlayer/recipe/EXT-MusicPlayer.js",
],
```

# `MMM-GoogleAssistant` Commands:
Activate you assistant and control music module with this command: 

* EN commands:
  * `music play`: play playlist music
  * `music pause`: make pause ;)
  * `music stop`: for stop it !
  * `music volume [0-100]`: for controling volume
  * `music next`: next music on the playlist
  * `music previous`: previous music on the playlist
  * `music rebuild`: rebuild music database
  * `music switch`: switch between USB Key and Local Files
 
* FR commands:
  * `musique play`: Lance la lecture de la playlist
  * `musique pause`: Mets la musique en pause
  * `musique stop`: Arret de la musique
  * `musique volume [0-100]`: Contrôle du volume
  * `musique suivante`: musique suivante
  * `musique précédente`: musique précédente
  * `musique base de donnée`: Actualise la base de donnée des titre a lire
  * `musique change source`: Change la source de lecture Clé USB <=> Fichier locaux

by editing `pattern` field in the recipe you can make the recipe for your language

# `EXT-TelegramBot` Commands:
You can control EXT-MusicPlayer with EXT-TelegramBot
The main command is `/music`

 * */music play*: Launch music (last title)
 * */music pause*: Pause music
 * */music stop*: Stop music
 * */music next*: Next track
 * */music previous*: Previous track
 * */music rebuild*: Rebuild music Database
 * */music volume*: Volume control, it need a value 0-100
 * */music switch*: Switch between USB Key and Local Folder
 * */music random*: Switch between random playing (toggle)

> ** In random playing mode: previous not working properly **
{.is-warning}


# Developer Notes
## Incoming notification:
 * `EXT_MUSIC-PLAY`: Start playing music
 * `EXT_MUSIC-STOP`: Stop music
 * `EXT_MUSIC-PAUSE`: Pause music
 * `EXT_MUSIC-NEXT`: Next track
 * `EXT_MUSIC-PREVIOUS`: Previous track
 * `EXT_MUSIC-REBUILD`: Rebuild music Database
 * `EXT_MUSIC-SWITCH: Rebuild music Database
 * `EXT_MUSIC-VOLUME_MIN`: Set volume to min (see config)
 * `EXT_MUSIC-VOLUME_MAX`: Sest volume to max (see config)
 * `EXT_MUSIC-VOLUME_SET`: Volume control with payload [0-100]
 
## Outgoing notification:
  * `EXT_MUSIC-CONNECTED`: When a music is playing
  * `EXT_MUSIC-DISCONNECTED`:  When music player is in rest

# User Notes

## What can music module can play ?
 Music module can play this format:
  * mp3
  * flac
  * wav
  * ogg
  * opus
  * m4a

## Visual
 * If a cover was found inside your music file, this module will descrypt it and display it
 * It will display all informations from the file

# Update
> For updating this module, just use this command:
{.is-success}

```
cd ~/MagicMirror/modules/EXT-MusicPlayer
npm run update
```