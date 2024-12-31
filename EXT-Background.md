---
title: EXT-Background
description: 
published: true
date: 2024-12-31T00:39:10.789Z
tags: 
editor: markdown
dateCreated: 2022-02-28T17:21:00.052Z
---

This module is an plugin for MMM-GoogleAssistant

It allows to change the default Google Assistant fullscreen background mode to your own or with animated gifs for each status of the assistant

# Screenshot
  Actually, i have prepared 4 models:
  
  - jarvis:<br>
    ![](https://raw.githubusercontent.com/bugsounet/EXT-Background/master/jarvis/standby.gif)
  - lego:<br>
    ![](https://raw.githubusercontent.com/bugsounet/EXT-Background/master/lego/standby.gif)
  - old:<br>
    ![](https://raw.githubusercontent.com/bugsounet/EXT-Background/master/old/standby.gif)
  - cortana:<br>
    ![](https://raw.githubusercontent.com/bugsounet/EXT-Background/master/cortana/standby.gif)

# Installation:

Execute `npm run install:EXT-Background` in the MMM-GoogleAssistant's folder.

```sh
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run install:EXT-Background
```

# Configuration

```js
{
  module: "MMM-GoogleAssistant/EXTs/EXT-Background",
  config: {
    model: "jarvis",
    myImage: null
  }
},
```

> | Option  | Description | Type | Default |
> | ------- | --- | --- | --- |
> | model | model of the animated background (jarvis, lego, old or cortana) | String | jarvis |
> | myImage | Name of the file of your own prefered background | String | null |

> Notes for `myImage` feature:
>
> If you set it, model is ignored !
> Past your prefered background file in the root directory of EXT-Background
> For the file name: Pay attention to upper and lower case letters
{.is-warning}


# Creation of a model

GoogleAssistant have some `Status`: listen, standby, confirmation, reply, error, hook<br>
This modules will read it<br>
So we can apply a gif to all status !

* Make a directory with the name of the new model
* Past all wanted GIFs to apply
* Rename your GIF for reading with the status<br>
 Names of files MUST be:
   * listen.gif 
   * standby.gif
   * confirmation.gif
   * reply.gif
   * error.gif
   
> If a gif is missing: it return a black screen for the missing status GIF
{.is-warning}

Now, you have just to select your model in your configuration

You can Make a PullRequest with your own model !

# Update
```sh
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run update
```

# Uninstall
```sh
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run remove:EXT-Background
```