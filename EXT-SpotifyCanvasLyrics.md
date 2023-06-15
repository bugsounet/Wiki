---
title: EXT-SpotifyCanvasLyrics
description: 
published: true
date: 2023-03-12T19:56:40.129Z
tags: 
editor: markdown
dateCreated: 2022-09-19T15:43:39.032Z
---

This Plugins will create a server for fetch Lyrics and Canvas (small video of a song)
 
 # plugins Requirements
  * EXT-Spotify
  * EXT-Librespot or EXT-Raspotify
  * EXT-Alert

 # Screenshot
 
Landscape mode:
 
![1661380128355-a614b0f1-142b-4d9e-b105-eae823e958ae-image.png](/1661380128355-a614b0f1-142b-4d9e-b105-eae823e958ae-image.png)
---
Portrait mode:

![1661976384550-ede2f383-90f2-422d-b6fb-389a3972203c-image.png](/1661976384550-ede2f383-90f2-422d-b6fb-389a3972203c-image.png)

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
> `/lyrics off`: Close display Canvas/Lyrics mode (except when MAgicMirror device is playing)
{.is-info}
 
 # Update
 
 ```sh
 cd ~/MagicMirror/modules/EXT-SpotifyCanvasLyrics
 npm run update
 ```
