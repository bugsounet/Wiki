---
title: EXT-Welcome
description: 
published: true
date: 2023-06-15T20:06:58.846Z
tags: 
editor: markdown
dateCreated: 2022-03-01T17:38:01.548Z
---

It allow to send a welcome on start of MagicMirror

> This module is an plugin for `MMM-GoogleAssistant`
{.is-info}

# Installation
Clone the module into your MagicMirror module folder and execute `npm intall` in the module's directory.
```
cd ~/MagicMirror/modules
git clone https://github.com/bugsounet/EXT-Welcome
cd EXT-Welcome
npm install
```

# Configuration

> To display the module insert it in the config.js file.
{.is-info}

```js
{
  module: 'EXT-Welcome',
  config: {
    welcome: "brief Today"
  }
},
```

> | Option  | Description | Type | Default |
> | ------- | --- | --- | --- |
> | welcome | define your welcome query | String | brief today |

# Update
```
cd ~/MagicMirror/modules/EXT-Welcome
npm run update
```

