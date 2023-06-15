---
title: EXT-SelfiesViewer
description: 
published: true
date: 2023-06-15T20:03:50.952Z
tags: 
editor: markdown
dateCreated: 2022-11-21T20:47:41.688Z
---

This plugins allow to display your local selfies directory in MagicMirror

> This plugins is an Extented plugins for `MMM-GoogleAssistant` , and `EXT-Selfies`
{.is-info}


> In addition, you can use EXT-Alert plugin, for display some information or error on your screen (Optional)
{.is-warning}

# Installation
Clone the module into your MagicMirror module folder and execute `npm intall` in the module's directory.
```
cd ~/MagicMirror/modules
git clone https://github.com/bugsounet/EXT-SelfiesViewer
cd EXT-SelfiesViewer
npm install
```

# Configuration
> To display the module insert it in the config.js file.
{.is-info}


```js
{
  module: 'EXT-SelfiesViewer',
  position: 'top_left',
  config: {
    debug: false,
    moduleWidth: 300,
    moduleHeight: 250,
    displayDelay: 1000 * 10,
    displayBackground: true,
    sortBy: "new" // old or random
  }
},
```

## Details

> |field | description | type | default value
> |---|---|---|---
> |debug | Enable debug mode or not | BOOLEAN | false
> |moduleHeight | module Height in px | NUMBER | 300
> |moduleWidth | module Width in px | NUMBER | 300
> |displayDelay | Delay before displaying next selfie (default is 10 secs) | NUMBER | 10 * 1000
> |displayBackground | Displaying a blurred decoration of the photo | BOOLEAN | true
> |sortBy | Sort received selfies by `new`, `old` or `random` | STRING | new

# Update
> For updating this module, just use this command:
{.is-success}

```
cd ~/MagicMirror/modules/EXT-SelfiesViewer
npm run update
```
