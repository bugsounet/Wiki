---
title: EXT-Bring
description: 
published: true
date: 2023-03-28T15:18:17.874Z
tags: 
editor: markdown
dateCreated: 2022-03-19T10:05:56.642Z
---

This plugin show your current shopping list on MagicMirror

> This module is an Extented plugins for `MMM-GoogleAssistant`
{.is-info}

> In addition, you can use some plugins:
> `EXT-Alert` for display some information or error on your screen (Optional)
{.is-warning}

# Informations

> *The module is not released by the Bring! company*
{.is-warning}

You need to create a email/password account on the `Bring!` [website](https://web.getbring.com/) to use this module.

The module was created using the REST api they use on their web site by reverse engineering it.

It is absolutely unsupported by the bring team.

# Installation

Clone the module into your MagicMirror module folder and execute `npm intall` in the module's directory.
```
cd ~/MagicMirror/modules
git clone https://github.com/bugsounet/EXT-Bring
cd EXT-Bring
npm install
```

# Configuration
> To display the module insert it in the config.js file.
{.is-info}


```js
{
    module: 'EXT-Bring',
    position: 'top_right',
    config: {
      debug: false,
      listName: "Liste",
      email: "someone@example.com",
      password: "secret",
      lang: 0,
      columns: 3,
      maxRows: 5,
      updateInterval: 30000,
      showBackground: true,
      showBox: true,
      showHeader: true
    }
},
```

<br>

## Configuration options

> Description of config feature
{.is-info}


| Option           | Description | Type | default
|----------------- |----------- |---|---
| `debug`          | *Optional* Enable Log level | Boolean | false
| `listName`       | *Required* The name of the List you want to display. Please make sure this matches EXACTLY. The Name is case sensitive. | String | null
| `email`          | *Required* The email adress to log in to your bring account | String | null
| `password`       | *Required* The password to log in to your bring account | String | null
| `lang`           | *Required* Your language code number | Number | 0
| `columns`        | *Optional* The number of colums in the table view  | Number | 4
| `maxRows`        | *Optional* The maximum number of rows to display in the table view |  Number | 5
| `updateInterval` | *Optional* The update frequency in milliseconds. |  Number | 30000
| `showBackground` | *Optional* Display a Background around item place or not | Boolean | true
| `showBox`        | *Optional* Display a Box around items | Boolean | true
| `showHeader`     | *Optional* Display the name of the shopping list in header of the plugin | Boolean | true

<br>

## `lang` code number

> Determinate your code number language and replace it in config
{.is-info}


| Number  | Language
|---------|-----------
|  0 | French (default)
|  1 | German from austria
|  2 | Swiss German
|  3 |  German
|  4 | Spanish
|  5 | British english
|  6 | American english
|  7 | Canadian english
|  8 | Australian english
|  9 | French from switzerland
|  10 | French
|  11 | Italian from switzerland
|  12 | Italian
|  13 | portuguese
|  14 | Dutch
|  15 | Hungarian
|  16 | Norwegian
|  17 | Polish
|  18 | Russian
|  19 | Swedish
|  20 | Turkish

<br>

# Update

```
cd ~/MagicMirror/modules/EXT-Bring
npm run update
```
