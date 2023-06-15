---
title: EXT-Governor
description: 
published: true
date: 2023-03-27T15:53:21.472Z
tags: 
editor: markdown
dateCreated: 2022-02-26T21:51:53.323Z
---

EXT-Governor is a plugins for control your CPU

> CPU governor enables the operating system to scale the CPU frequency up or down in order to save power or improve performance.
{.is-info}


> This module an Extented plugin of `EXT-Screen`
{.is-warning}

It can be used to send a Maximum of power when your screen is ON
In reverse, an economy mode, when your screen if OFF

# Installation
Needed:
  * MagicMirror v2.22.0 and above
  * Node v16.x
  * npm v8.x

Clone the module into your MagicMirror module folder and execute `npm intall` in the module's directory.
```
cd ~/MagicMirror/modules
git clone https://github.com/bugsounet/EXT-Governor
cd EXT-Governor
npm install
```

# Configuration
> insert your configuration in the config.js file of MagicMirror.
{.is-info}


```js
{
  module: 'EXT-Governor',
  config: {
    debug: false,
    sleeping: "powersave",
    working: "ondemand"
  }
},
```

> | Option  | Description | Type | Default |
> | ------- | --- | --- | --- |
> | debug | enable or not debug mode | Boolean | false |
> | sleeping | name of the governor when screen is in sleeping state | String | powersave |
> | working | name of the governor when screen is actived | String | ondemand |

Available governor:
 * conservative
 * ondemand
 * userspace
 * powersave
 * performance
 
> Notes: On each boot of your RPI, your governor is set automaticaly to `ondemand`
{.is-warning}

> If you want a maximum of CPU power, `performance` is the best choice !
> If you want an economy mode of CPU power, `powersave` is the best choice !
> The default mode is designed with `ondemand`
{.is-success}

> With the configuration by default, only eco-mode is activated.
> Try changing the values and see the difference !
{.is-info}



# Developer Notes

- This module receive:
  * `EXT_GOVERNOR-WORKING`: enable the governor of the `working` configuration. 
  * `EXT_GOVERNOR-SLEEPING`: enable the governor of the `sleeping` configuration.

# Update
```
cd ~/MagicMirror/modules/EXT-Governor
npm run update
```
