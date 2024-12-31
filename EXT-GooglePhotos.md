---
title: EXT-GooglePhotos
description: 
published: true
date: 2024-12-31T00:43:52.379Z
tags: 
editor: markdown
dateCreated: 2022-03-05T10:55:05.341Z
---

EXT-GooglePhotos

This plugin allows to display your album directory with Google photos API in background or in MagicMirror position

> This plugin is an Extented plugins for `MMM-GoogleAssistant`
{.is-info}

# Installation

Execute `npm run install:EXT-GooglePhotos` in the MMM-GoogleAssistant's folder.
```
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run install:EXT-GooglePhotos
```

## Google credentials (`credendials.json`)

This module need google credentials file
You can create it with following this [wiki part](https://wiki.bugsounet.fr/MMM-GoogleAssistant/SetupCredentials).
Save the result file and rename it to `credentials.json` file into the root of this module (inside your EXT-GooglePhotos folder)

> If you have already create it with `MMM-GoogleAssistant`, this module will search it automaticaly and use it.
> So it's not necessary to create it or past it
{.is-success}

## Token Create

We have to install a new API from the google developers console

1) You have to activate the [Photos Library API](https://console.cloud.google.com/apis/library/photoslibrary.googleapis.com?q=Google%20photos)
2) Install the token for Google Photo API using:

In a terminal on the RPI desktop (NOT in SSH), type this command:
 
```sh
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run token:EXT-GooglePhotos
```

Naturally, authorise all conditions.

The token will be created as `tokenGP.json` in the root directory of this module

# Configuration
> To display the module insert it in the config.js file.
{.is-info}


```js
{
  module: 'MMM-GoogleAssistant/EXTs/EXT-GooglePhotos',
  position: 'top_left',
  animateIn: 'backInLeft',
  animateOut: 'backOutRight',
  config: {
    debug: false,
    displayType: 0,
    displayDelay: 10 * 1000,
    displayInfos: true,
    displayBackground: true,
    albums: [],
    sort: "new", // "old", "random"
    hiResolution: true,
    timeFormat: "DD/MM/YYYY HH:mm",
    moduleHeight: 300,
    moduleWidth: 300,
    uploadAlbum: null
  }
},
```

## Details

> |field | description | type | default value
> |---|---|---|---
> |debug | Enable debug mode or not | BOOLEAN | false
> |displayType | How displaying Google Photos? (`0`: in Fullscreen, `1`: in MagicMirror position)| NUMBER |  0
> |displayDelay | Delay before displaying next photo in the iframe (default is 10 secs) | NUMBER | 10 * 1000
> |displayInfos | Displaying name of the album and photo time | BOOLEAN | true
> |displayBackground | Displaying a blurred decoration of the photo | BOOLEAN | true
> |albums: | Folders of Google Photos to display | ARRAY Of STRING | []
> |sort | Sort received google photos `new`, `old`, `random` | STRING | new
> |hiResolution | Displaying photos in Hi-Resolution | BOOLEAN | true
> |timeFormat | Time/ date Format | STRING | DD/MM/YYYY HH:mm
> |moduleHeight | module Height in px | NUMBER | 300
> |moduleWidth | module Width in px | NUMBER | 300
> |uploadAlbum | Name of the album to upload any photos | STRING | null

> `albums` feature: You can add one or more albums
>  Sample:
>
>  `albums: ["album1"],`
>  `albums: ["album1", "2020"],`
{.is-info}

# animateIn / animateOut

You are able now to use animate feature for transition
Read MagicMirror² [animated](https://docs.magicmirror.builders/modules/configuration.html#animated) functionality

# Update
> For updating this module, just use this command:
{.is-success}

```
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run update
```

# Uninstall
```sh
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run remove:EXT-GooglePhotos
```