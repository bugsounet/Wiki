---
title: EXT-FreeboxTV
description: 
published: true
date: 2024-12-31T00:43:08.898Z
tags: 
editor: markdown
dateCreated: 2022-02-28T22:52:43.251Z
---

EXT-FreeboxTV

> Ce module nécessite le plugin `EXT-VLCServer` pour visionner une chaine de TV
{.is-warning}

Il permet d'afficher, sur votre Mirroir, les chaines de TV de la [Freebox](https://www.free.fr/freebox/).


> Voici les chaines actuellement disponibles:
{.is-info}


| Pseudonyme  | Nom de la Chaine |
| ------- | ------ |
| France2 | France 2 |
| France3 | France 3 |
| France4 | France 4 |
| France5 | France 5 |
| ARTE | ARTE |
| C8 | C8 |
| NRJ12 | NRJ 12 |
| LCP | La Chaine Parlementaire |
| BFMTV | BFM TV |
| CNews | C NEWS |
| CStar | C Star |
| Gulli | Gulli (uniquement en plein écran) |
| Equipe | L'équipe |
| RMCStory | RMC Story |
| RMCDecouverte | RMC Découverte |
| Cherie25 | Chérie 25 |
| FranceInfo | France Info |
| ParisPremiere | Paris Première |
| RTL9 | RTL9 |
| GameOne | Game One |
| AB1 | AB1 |
| TEVA | Téva |
| M6Music | M6 Music |
| MCM | MCM |
| Mangas | Mangas |
| Equidia | Equidia |
| AutoMoto | Auto Moto |
| RFMTV | RFM TV |

# Screenshoot
![](https://raw.githubusercontent.com/bugsounet/MMM-GoogleAssistant/dev/EXTs/EXT-FreeboxTV/resources/screenshoot.jpg)

# Piloter le module

Ce module peut-être piloter avec:

 >  * MMM-GoogleAssistant afin de transmettre l'ordre de changement de chaine en vocal
 >  * EXT-TelegramBot pour commander le changement de chaine, volume ou l'arrêt de la TV
 >  * Par socketNotification (pour developeur)

# Installation
> Exécutez `npm run install:EXT-FreeboxTV` dans le répertoire de MMM-GoogleAssistant.

```sh
cd ~MagicMirror/modules/MMM-GoogleAssistant
npm run install:EXT-FreeboxTV
```

## MMM-GoogleAssistant
> Ajouter le recipe `EXT-FreeboxTV.js` dans la configuration du module de MMM-GoogleAssistant
{.is-info}

 
```js
{
  module: "MMM-GoogleAssistant",
  config: {
  ...
    recipes: [ 
      "../EXTs/EXT-FreeboxTV/recipe/EXT-FreeboxTV.js"
    ],
  ...
  }
},
```
> naturellement, si vous avez d'autres recipes, il suffit de le mettre à la suite
{.is-success}

```js
recipes: [ 
  "with-exemple_de_recipes.js",
  "../EXTs/EXT-FreeboxTV/recipe/EXT-FreeboxTV.js"
],
```

# Configuration
> Pour afficher le module, inserez ceci dans votre ficher `config.js`
{.is-info}


```js
{
  module: 'MMM-GoogleAssistant/EXTs/EXT-FreeboxTV',
  configDeepMerge: true,
  config: {
    debug: false,
    streams: "streamsConfig.json",
    volume : {
      start: 100,
      min: 30,
      useLast: true
    }
  }
},
```

>| Option  | Description | Type | Defaut |
>| ------- | --- | --- | --- |
>| debug | Active le mode de debuguage | Booléen | false |
>| streams | Nom du fichier contenant les streams des chaines (format JSON) | STRING | streamsConfig.json |
<br>

## Champ `volume: {}`
>| Option  | Description | Type | Defaut |
>| ------- | --- | --- | --- |
>|-start| volume au démarrage TV (entre 0 et 100) | Nombre | 100|
>|-min| volume en cas d'utilisation de l'assistant | Nombre | 30|
>|-useLast| Utilise le dernier volume utilisé | Booléen | true |

UseLast va permettre memoriser le dernier volume utilisé (avec la commande vocale ou avec `/TVol` de telegramBot), si vous activez la fonction.

# Demander un changement de chaine
Activer votre assistant avec votre mot clé préféré et dites `TV <nom de la chaine>`
exemple: `Jarvis ... TV France 2`

# Demander le controle du volume
Activer votre assistant et dites `TV Volume <volume>%`
exemple: `jarvis ... TV Volume 50%`

# Demander l'arrêt
Activer votre assistant avec votre mot clé préféré et dites `TV stop`

# TelegramBot
> Voici la liste des commandes:
{.is-info}

 * `/TV <numéro de chaine` : Zappe sur le numéro de la chaine demandé
 * `/TV`: Stop le stream TV
 * `/TVol`: Contrôle du volume de la TV (entre 0 et 100)
 * `/TVList`: Liste les chaine disponible


# Options developpeur:
> Notification entrante:
{.is-info}

 * `EXT_FREEBOXTV-PLAY` payload: \<pseudonyme de la chaine\> -> Permet de visualiser la chaine
 * `EXT_FREEBOXTV-STOP` -> Permet l'arrêt
 * `EXT_FREEBOXTV-VOLUME` payload: \<nombre entre 0 et 100\> -> Permet le changement du volume
 * `EXT_FREEBOXTV-NEXT` -> Permet de mettre la chaine suivante
 * `EXT_FREEBOXTV-PREVIOUS` -> Permet de mettre la chaine precedente

> Notification Sortante:
{.is-info}

 * `EXT_FREEBOXTV-CONNECTED`: Confirme par cette notification l'activation de la TV
 * `EXT_FREEBOXTV-DISCONNECTED`: Confirme par cette notification l'arrêt de la TV

# Update
```sh
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run update
```

# Uninstall
```sh
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run remove:EXT-FreeboxTV
```