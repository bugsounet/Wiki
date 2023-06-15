---
title: configuration Sample
description: 
published: true
date: 2021-07-03T14:36:21.942Z
tags: 
editor: markdown
dateCreated: 2021-06-22T17:38:30.656Z
---

# Configuration Sample

## Simple

This is a sample configuration.<br>
With this default configuration, it will display the default rss feed of @bugsounet modules news (update, news modules, ...)

```js
    {
      module: "MMM-NewsFeed",
      position: "bottom_bar",
      configDeepMerge: true
    },
```

# Complete for personalize

See [[Configuration Structure]] for descriptions of each field

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
        flux: [
          {
            from: "New York Times",
            url: "https://rss.nytimes.com/services/xml/rss/nyt/HomePage.xml"
          },
          {
            from: "4th Party Modules",
            url: "http://forum.bugsounet.fr/category/1.rss"
          }
        ],
        personalize: {
          Name: "NewsFeed",
          NameField: true,
          NameColor: "#FFF",
          NameBackground: "#414141",
          ArticleColor: "#000",
          ArticleBackground: "#AAA",
          DescriptionColor: "#000",
          DescriptionBackground: "#FFF",
          QRCode: true,
          fontSize: "100%"
        },
        vertical: {
          useVertical: false,
          width: "450px",
          imageMaxWidth: "20vw",
          imageMaxHeight: "20vh"
        }
      }
    },
```