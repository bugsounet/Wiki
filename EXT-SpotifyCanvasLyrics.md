---
title: EXT-SpotifyCanvasLyrics
description: 
published: true
date: 2024-08-12T15:20:03.293Z
tags: 
editor: markdown
dateCreated: 2022-09-19T15:43:39.032Z
---

This Plugins will create a server for fetch Lyrics and Canvas (small video of a song)
 
 # plugins Requirements
  * EXT-Spotify
  * EXT-Librespot
  * EXT-Alert

 # Screenshot
 
Landscape mode:

![landscape.png](/resources/spotifycanvaslyrics/landscape.png)
---
Portrait mode:

![portrait.png](/resources/spotifycanvaslyrics/portrait.png)

 # Installation:
 
 ```sh
 cd ~/MagicMirror/modules/
 git clone https://github.com/bugsounet/EXT-SpotifyCanvasLyrics
 cd EXT-SpotifyCanvasLyrics
 npm install
 ```
 
 # Configuration
 
```js
    {
        module: 'EXT-SpotifyCanvasLyrics'
    },
 ```
 
 This plugins have no position and no configuration !
 It will be auto-configured with all requirements
 
 # Screen Touch Using
 
 `EXT-SpotifyCanvasLyrics` displayer can react with you touch screen
 
 * Touchable button:
    * Play
    * Pause
    * Next
    * Previous
    * Next
    * Repeat
    * Shuffle
  
  * You can change device with the device button !
    * A popup will be displayed with all device available.
  
  * Seek Bar (or Progress Bar) is in touch mode. 
    * If you want to seek, just press at the desired position
  
  * Volume bar Touch mode
    * Like seek bar, volume bar can control the volume

  * Return to Normal `EXT-Spotify` mode
    * Click on Spotify logo
    * Note: Don't work when the MagicMirror device is playing
    
  * In normal EXT-Spotify mode
    * Click on the cover to display `EXT-SpotifyCanvasLyrics` mode

 # EXT-TelegramBot Command
 `EXT-SpotifyCanvasLyrics` have a telegramBot command.
 
 Just try `/lyrics`:
 
> `/lyrics on`: Force to display Canvas/Lyrics mode
> `/lyrics off`: Close display Canvas/Lyrics mode (except when MagicMirror² device is playing)
{.is-info}

> `/lyrics` commands are used for displaying (or not) Lyrics when music is playing from another device (Phone,TV,…)
> `/lyrics off` is inactive when music is playing from MM²
{.is-warning}


 # Update
 
 ```sh
 cd ~/MagicMirror/modules/EXT-SpotifyCanvasLyrics
 npm run update
 ```
