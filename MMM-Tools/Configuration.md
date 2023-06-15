---
title: Configuration
description: 
published: true
date: 2022-04-20T17:30:54.457Z
tags: 
editor: markdown
dateCreated: 2021-07-14T11:46:31.737Z
---

# Minimal Sample configuration

> use config.js file of MagicMirror for configuring MMM-Tools
{.is-info}


```js
{
  module: 'MMM-Tools',
  position: 'top_right',
  config: {
    refresh: 1000 * 5,
    containerSize: null,
    itemSize: null
  }
},
```

# Full Sample configuration

> This is the default configuration defined if you don't define any value.
> You can use it for a personalized configuration.
> Of course, you can only add your personalized part !
{.is-warning}


```js
{
  module: 'MMM-Tools',
  position: 'top_right',
  config: {
    containerSize: null,
    itemSize: null,
    MM: {
      displayMM: true,
      orderMM: 0
    },
    NODE: {
      displayNode: true,
      orderNode: 1
    },
    NPM: {
      displayNpm: true,
      orderNpm: 2
    },
    OS: {
      displayOs: true,
      displayArch: true,
      orderOs: 3
    },
    CPU: {
      displayUsage: true,
      orderUsage: 8,
      displaySpeed: true,
      orderSpeed: 5,
      displayGovernor: true,
      orderGovernor:6,
      displayTemp: true,
      celciusTemp: true,
      orderTemp: 11,
      displayType: true,
      orderType: 4
    },
    RAM: {
      displayRam: true,
      orderRam: 9
    },
    STORAGE: {
      displayStorage: true,
      orderStorage: 10,
      partitionExclude : []
    },
    NETWORK: {
      displayNetwork: true,
      orderNetwork: 7,
      nativeNetwork: true,
      displayDefaultNetwork: true
    },
    UPTIME: {
      displayUptime: true,
      useMagicMirror: true,
      orderUptime: 12,
      displayRecord: true,
      orderRecord: 13
    },
    WARNING: {
      enableWarning: false,
      interval: 1000 * 60 * 5,
      check : {
        CPU_TEMP : 65,
        CPU_USAGE : 75,
        STORAGE_USED : 80,
        MEMORY_USED : 80,
      }
    }
  }
},
```

For description of any features, please read [Configuration Structure](/MMM-Tools/ConfigurationStructure)