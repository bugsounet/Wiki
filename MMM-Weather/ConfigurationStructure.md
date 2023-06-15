---
title: Configuration Structure
description: 
published: true
date: 2022-10-01T08:05:24.059Z
tags: 
editor: markdown
dateCreated: 2021-07-10T21:35:10.796Z
---

# Basic structure
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
      key: "my_own_key",
      latitude: 50.104321,
      longitude: 4.759645,
    },
    ...
  }
},
```

# [Configurable filed](/en/MMM-Weather/ConfigurationSample#full-detailed-see-the-configuration-structure) 

> You don't need to use all of these, Because all of them be set as default value. Just pick what you need then override in your `config.`
{.is-warning}


## Field `debug`
> |field | type | default value
> |---|---|---
> |debug | BOOLEAN | false

When you set `debug` to `true`, detailed log will be recorded. When you don't want log, set it to `false`

### Field `updateInterval`
> |field | type | default value
> |---|---|---
> |updateInterval | STRING | 15m

How frequently, in minutes, to fetch data. (default is "15m")

## Field `updateFadeSpeed`
> |field | type | default value
> |---|---|---
> |updateFadeSpeed | NUMBER | 500

How quickly in milliseconds to fade the module out and in upon data refresh. Set this to 0 for no fade.

## Field `newAccount`
> |field | type | default value
> |---|---|---
> |newAccount | BOOLEAN | false

If you just create an new account, we have to use onecall v3.0 API
Register a free onecall account too for enable onecall using
And enable `newAccount` feature to `true`

> We have to do a subscription for using onecall v3.0 API
> by default you will received an default “One Call” account
> and you can use it
> BUT it’s limited to 2000 calls by days AND 60 calls by minutes
> after 2000 calls by days, you will paid 0.14 EUR per 100 mores calls
{.is-info}

> By default, `MMM-Weather` will update every 15 minutes
> it’s means :
> 4 updates by hours
> 4*24hours -> 96 calls by days
> I think, it’s should be ok with this timer ;)
{.is-success}

> WARN: don’t forget that if you use MM² in server mode (open mm² with a browser) you will open an new instence of update
> it’s the same like you launch another MM² app !
> So … 96 calls x each new instance !
> if you launch 2 instances: 96 * 2 = 192 calls by days !
{.is-warning}


## Field `api: {}`
> |field (- subFiled) | type | default value
> |---|---|---
> |api |  OBJECT | { ... }
> |- key | STRING | null
> |- latitude | NUMBER | null
> |- longitude | NUMBER | null
> |- units | STRING | default units configuration of MagicMirror
> |- language |STRING | default language configuration of MagicMirror

- `key`: your openweather api key. Get an API key at https://openweathermap.org/
- `latitude`: your longitude
- `longitude`: your latitude
- `units`: The units to be used to display, default units is MagicMirror value (optional)
- `language`: The language to be used for display, default language is MagicMirror value (optional)

> Note: 
>  For `latitude` and `longitude`, This [website](https://latitudelongitude.org/) can help you to determinate it
>  `units` and `language` have only to be setted if you want to change units or language !
{.is-success}


## Field `display: {}`
> |field (- subFiled) | type | default value
> |---|---|---
> |display |  OBJECT | { ... }
> |- CurrentConditions  | BOOLEAN | true
> |- ExtraCurrentConditions | BOOLEAN | true
> |- Summary | BOOLEAN | true
> |- ForecastTableColumnHeaderIcons | BOOLEAN | true
> |- HourlyForecast | BOOLEAN | true
> |- DailyForecast | BOOLEAN | true
> |- Precipitation | BOOLEAN | true
> |- Wind | BOOLEAN | true
> |- InlineIcons | BOOLEAN | true
> |- Feels | BOOLEAN | true
> |- SunCondition | BOOLEAN | true
> |- Humidity | BOOLEAN | true
> |- UV | BOOLEAN | true
> |- Beaufort | BOOLEAN | true
{.is-info}


- `CurrentConditions`: show current temperaure and current conditions icon.
- `ExtraCurrentConditions`: show additional current conditions such as high/low temperatures, precipitation and wind speed.
- `Summary`: show the forecast summary
- `ForecastTableColumnHeaderIcons`: show icons column headers on the forecast table.
- `HourlyForecast`: show hourly forecast information.
- `DailyForecast`: show daily forecast information.
- `Precipitation`: show precipitation information.
- `Wind`: show wind information.
- `InlineIcons`: show prefix wind and precipitation information with an icon.
- `Feels`: show feels information.
- `SunCondition`: show sunrise and sunset information
- `Humidity`: show humidity information
- `UV`: show ultraviolet information
- `Beaufort`: show colored wind arrow icon with beaufort unit

## Field `personalize: {}`
> |field (- subFiled) | type | default value
> |---|---|---
> |personalize |  OBJECT | { ... }
> |- hourlyForecastInterval  | NUMBER | 3
> |- maxHourliesToShow | NUMBER | 3
> |- maxDailiesToShow | NUMBER | 3
> |- concise | BOOLEAN | false
> |- colored | BOOLEAN | true
> |- forecastLayout | STRING | table
> |- forecastHeaderText | STRING | null

- `hourlyForecastInterval`: How many hours apart each listed hourly forecast is.
- `maxHourliesToShow`: How many hourly forecasts to list.
- `maxDailiesToShow`: How many daily forecasts to list.
- `concise`: When set to true, this presents less information. (e.g.: shorter summary, no precipitation accumulation, no wind gusts, etc.)
- `colored`: Whether to present module in colour or black-and-white. Note, if set to false, the monochramtic version of your chosen icon set will be forced.
- `forecastLayout`: Can be set to tiled or table. How to display hourly and forecast information.
- `forecastHeaderText`: Show a header above the forecast display.

## Field `labels: {}`
> |field (- subFiled) | type | default value
> |---|---|---
> |labels |  OBJECT | { ... }
> |- high | STRING | H
> |- low | STRING | L
> |- timeFormat | STRING | "k[h]"

- `high`: The label you wish to display for prefixing high temperature.
- `low`: The label you wish to display for prefixing low temperature.
- `timeFormat`: How you want the time formatted for hourly forecast display. Accepts any valid moment.js format (https://momentjs.com/docs/#/displaying/format/). For example, for am/pm format use "h a" (e.g.: 9 am)