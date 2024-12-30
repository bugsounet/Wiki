---
title: EXT-Welcome
description: 
published: true
date: 2024-12-30T11:56:25.520Z
tags: 
editor: markdown
dateCreated: 2022-03-01T17:38:01.548Z
---

It allow to send a welcome on start of MagicMirror

> This module is an plugin for `MMM-GoogleAssistant`
{.is-info}

# Installation
Execute `npm run install:EXT-Welcome` in the MMM-GoogleAssistant's folder.
```
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run install:EXT-Welcome
```

# Configuration

> To display the module insert it in the config.js file.
{.is-info}

```js
{
  module: 'MMM-GoogleAssistant/EXTs/EXT-Welcome',
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
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run update
```

