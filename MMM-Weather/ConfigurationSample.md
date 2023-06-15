---
title: Configuration Sample
description: 
published: true
date: 2022-10-01T07:42:09.204Z
tags: 
editor: markdown
dateCreated: 2021-07-10T21:29:38.457Z
---

use `config.js` file of MagicMirror for configuring MMM-Weather
# Simple
```js
{  
  module: "MMM-Weather",
  position: "top_right",
  configDeepMerge: true,
  config: {
    updateInterval: "15m", // 15 minutes
    newAccount: false,
    api: {
      key: "my_own_key",
      latitude: 50.104321,
      longitude: 4.759645,
    },
  }
},
```

# Full & Detailed (See the `Configuration Structure`)
This is the default configuration defined if you don't define any value
```js
{  
  module: "MMM-Weather",
  position: "top_right",
  configDeepMerge: true,
  config: {
    debug: false,
    updateInterval: "15m", // 15 minutes
    updateFadeSpeed: 500,
    newAccount: false,
    api: {
      key: "",
      latitude: "",
      longitude: "",
      //units: config.units,
      //language: config.language
    },
    display: {
      CurrentConditions: true,
      ExtraCurrentConditions: true,
      Summary: true,
      ForecastTableColumnHeaderIcons: true,
      HourlyForecast: true,
      DailyForecast: true,
      Precipitation: true,
      Wind: true,
      InlineIcons: true,
      Feels: true,
      SunCondition: true,
      Humidity: true,
      UV: true,
      Beaufort: true
    },
    personalize: {
      hourlyForecastInterval: 3,
      maxHourliesToShow: 3,
      maxDailiesToShow: 3,
      concise: false,
      colored : true,
      forecastLayout: "table",
      forecastHeaderText: ""
    },
    labels: {
      high: "H",
      low: "L",
      timeFormat: "kk[h]"
    }
  }
},
```