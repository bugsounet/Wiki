---
title: configuration Structure
description: 
published: true
date: 2021-07-03T14:35:14.009Z
tags: 
editor: markdown
dateCreated: 2021-06-22T17:41:12.498Z
---

> From complete configuration, full description of each field:
{.is-info}


```js
    {
      module: "MMM-NewsFeed",
      position: "bottom_bar",
      configDeepMerge: true,
      config: {
        debug:false,
        update: "15m",
        speed: "15s",
        maxItems: 100,
        ...
      }
    },
```

> You don't need to use all of these, Because all of them be set as default value. Just pick what you need then override in your `config.`
{.is-warning}


## Field `debug`
|field | type | default value
|---|---|---
|debug | BOOLEAN | false

When you set `debug` to `true`, detailed log will be recorded. When you don't want log, set it to `false`

## Field `update`
|field | type | default value
|---|---|---
|update | STRING | "15m"

Delay frequency, in minutes, fetch all datas (default is 15 minutes)

## Field `speed`
|field | type | default value
|---|---|---
|speed | STRING | "15s"

Delay frequency to display, in seconds, the news (default is 15 seconds)

## Field `maxItems`
|maxItems | type | default value
|---|---|---
|maxItems | NUMBER | 100

Max Item (or news) to display

## Field `flux: []`
This field is an array of the fetch data links, for displaying rss feed

By default it will be set with the `New York Times`

Sample with adding many rss feed:

```js
flux: [
  {
    from: "New York Times", // name of the feed
    url: "https://rss.nytimes.com/services/xml/rss/nyt/HomePage.xml", // url of your feed
    encoding: "UTF-8" // ISO-8859-1 Select your encoding type (UTF-8 by default)
  },
  {
    from: "Galantina",
    url: "https://www.galatina.it/rss.xml"
  },
  {
    from: "Ansa",
    url: "https://www.ansa.it/sito/notizie/topnews/topnews_rss.xml"
  },
  {
    from: "Feedburner",
    url: "http://feeds.feedburner.com/hd-blog?format=xml"
  },
  {
    from: "fxexchangerate",
    url: "https://eur.fxexchangerate.com/usd.xml"
  },
  {
    from: "SKY TG24",
    url: "https://tg24.sky.it/rss/tg24_flipboard.ultimenews.xml"
  },
  {
    from: "SKY Sport",
    url: "http://feeds.feedburner.com/SkyitSport"
  }
]
```

@bugsounet news is located with this config:
```
      {
        from: "4th Party Modules",
        url: "http://forum.bugsounet.fr/category/1.rss"
      }
```
you can add it, if you want ;)

## Field `personalize: {}`
|personalize | type | default value
|---|---|---
|Name | STRING | "NewsFeed"
|NameField | BOOLEAN | true
|NameColor | STRING | "#FFF"
|NameBackground |STRING | "#414141"
|ArticleColor |STRING | "#000"
|ArticleBackground |STRING | "#AAA"
|DescriptionColor |STRING | "#000"
|DescriptionBackground |STRING | "#FFF"
|QRCode | BOOLEAN | true
|fontSize| STRING | "100%"

* `Name`: Your prefered Text in the News Bar title (by default: "NewsFeed")
* `NameField`: Should display your prefered text ?
* `NameColor`: Color of your prefered text
* `NameBackground`: Background color of your prefered text
* `ArticleColor`: Color of the article bar
* `ArticleBackground`: Background color of the article bar
* `DescriptionColor`: Color of the article description
* `DescriptionBackground`: Background color of the article description
* `QRCode`: display the QRCode for opening the news with your phone
* `fontSize`: define your prefered font size

## Field `vertical: {}`
|vertical | type | default value
|---|---|---
|useVertical|BOOLEAN| false,
|width|STRING| "450px"
|imageMaxWidth|STRING| "20vw"
|imageMaxHeight|STRING| "20vh"

* `useVertical`: Use vertical configuration
* `width`: width (in px) of the module, if vertical use
* `imageMaxWidth`: Image Max Width, if vertical use
* `imageMaxHeight`: Image Max Height, if vertical use
