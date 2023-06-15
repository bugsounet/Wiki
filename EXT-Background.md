---
title: EXT-Background
description: 
published: true
date: 2023-05-19T09:58:49.692Z
tags: 
editor: markdown
dateCreated: 2022-02-28T17:21:00.052Z
---

This module is an plugin for MMM-GoogleAssistant

It allows to change the default Google Assistant fullscreen background mode to your own or with animated gifs for each status of the assistant

Needed: [MMM-GoogleAssistant](/en/MMM-GoogleAssistant)

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

Clone the module into your MagicMirror module folder and execute npm intall in the module's directory.

```sh
cd ~/MagicMirror/modules
git clone https://github.com/bugsounet/EXT-Background
cd EXT-Background
npm install
```

# Configuration

```js
{
  module: "EXT-Background",
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
```
cd ~/MagicMirror/modules/EXT-Background
npm run update
```