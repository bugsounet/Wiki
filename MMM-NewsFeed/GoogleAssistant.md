---
title: MMM-GoogleAssistant Recipe
description: 
published: true
date: 2022-06-12T15:01:43.011Z
tags: 
editor: markdown
dateCreated: 2022-06-12T14:58:05.121Z
---

> Since v1.2.0, MMM-NewsFeed can be controled with [MMM-GoogleAssistant](/en/MMM-GoogleAssistant)
{.is-success}


# `MMM-GoogleAssistant` recipe for vocal control
A prepared recipe is inclued and waiting for your use
Just add it in the config of MMM-GoogleAssistant

 * sample:
```js
recipes: [
  "../../MMM-NewsFeed/recipe/MMM-NewsFeed.js"
],
```
 * if you have other recipe, just add it like this:
```js
recipes: [
  "my_recipe.js",
  "../../MMM-NewsFeed/recipe/MMM-NewsFeed.js"
],
```
## How to use it ?

> This recipe can open the news in fullscreen, display next/previous news and refresh news database
{.is-info}


Activate your mirror with your prefered keyword and just say:

* EN commands:
 `Open News`: Open the news with the browser (`EXT-Browser` needed) 
 `Next News`: Display next news
 `Previous News`: Display previous news
 `Refresh News`: Refresh news database

* FR commands:
 `Ouvre l'article`: Ouvre l'article dans le navigateur (`EXT-Browser` est nécessaire) 
 `Article suivant`: Affiche l'article suivant
 `Article Précédent`: Affiche l'article précédent
 `Mets à jour les articles`: Met à jour la base de donnée des articles

Naturaly, you can do commands in your own language by editing the recipe file
In this case, don't forget to save it with another file name (Original file will be reset on each update)

