---
title: MMM-FranceInfo
description: 
published: true
date: 2021-07-03T09:55:16.790Z
tags: 
editor: markdown
dateCreated: 2021-07-03T09:50:05.767Z
---

Affiche les flux rss de `franceinfo:` sur MagicMirror

![](https://raw.githubusercontent.com/bugsounet/MMM-FranceInfo/dev/franceinfo.png)

# Screenshot

![](https://raw.githubusercontent.com/bugsounet/MMM-FranceInfo/main/FRINFO.png)

# Installation
```
cd ~/MagicMirror/modules
git clone https://github.com/bugsounet/MMM-FranceInfo
cd MMM-FranceInfo
npm install
```

# Configuration

## Simple:
```js
    {
      module: "MMM-FranceInfo",
      position: "bottom_bar",
      configDeepMerge: true
    }
```

## Personalisée
```js
    {
      module: "MMM-FranceInfo",
      position: "bottom_bar",
      configDeepMerge: true,
      config: {
        debug: false,
        update: "15m",
        speed: "15s",
        maxItems: 100,
        flux: [
          "Les Titres",
          //"Vidéos",
          //"Diaporamas",
          //"France",
          //"Politique",
          //"Société",
          //"Faits divers",
          //"Justice",
          "Monde",
          //"Afrique",
          //"Amériques",
          //"Europe",
          //"Proche Orient",
          //"Environnement",
          //"Tendances",
          //"Entreprises",
          //"Marchés",
          //"Immobilier",
          //"Sports",
          //"Foot",
          //"Rugby",
          //"F1",
          //"Découvertes",
          //"Sciences",
          //"Santé",
          //"Animaux",
          //"Bizarre",
          //"Buzz+",
          //"Médias",
          //"Cinéma",
          //"Musique",
          //"Internet"
        ],
        useQRCode: true,
        vertical: {
          useVertical: false,
          width: "450px",
          imageMaxWidth: "20vw",
          imageMaxHeight: "20vh"
        }
      }
    },
```

# Structure

## Champ `debug`
>|Champ | type | valeur par défaut
>|---|---|---
>|debug | BOOLEAN | false

Si vous définissez `debug` sur true `true`, les logs détaillé seront écrit en console. (généralement réservé aux développeurs)

## Champ `update`
>|Champ | type | valeur par défaut
>|---|---|---
>|update | STRING | "15m"

Temps d'intervale des mise a jours des information RSS. La valeur doit être exprimé en `h`, `m` et/ou `s` pour Heures, Minutes, Secondes.

## Champ `speed`
>|Champ | type | valeur par défaut
>|---|---|---
>|speed | STRING | "15s"

Temps d'affichage de l'article. La valeur doit être exprimé en `h`, `m` et/ou `s` pour Heures, Minutes, Secondes.

## Champ `maxItem`
>|Champ | type | valeur par défaut
>|---|---|---
>|maxItem | NUMBER | 100

Nombre d'article qui peuvent être affiché (Utilise en cas de plusieures requetes RSS)

## Champ `flux: []`
>|Champ | type | valeur par défaut
>|---|---|---
>|flux | ARRAY of STRING | [ "Les Titres" , "Monde" ]

32 Flux RSS disponible:
 * Les Titres
 * Vidéos
 * Diaporamas
 * France
 * Politique
 * Société
 * Faits divers
 * Justice
 * Monde
 * Afrique
 * Amériques
 * Europe
 * Proche Orient
 * Environnement
 * Tendances
 * Entreprises
 * Marchés
 * Immobilier
 * Sports
 * Foot
 * Rugby
 * F1
 * Découvertes
 * Sciences
 * Santé
 * Animaux
 * Bizarre
 * Buzz+
 * Médias
 * Cinéma
 * Musique
 * Internet

## Champ `useQRCode`
>|Champ | type | valeur par défaut
>|---|---|---
>|useQRCode | BOOLEAN | true

Affiche le QRCode relatif à l'article.

## Champ `vertical: {}`
>|Champ | type | valeur par défaut
>|---|---|---
>|vertical | Object | 
>|-useVertical | BOOLEAN | false
>|-width | STRING | 450px
>|-imageMaxWidth | STRING | 20vw
>|-imageMaxHeight | STRING | 20vh

- useVertical: utilisation du module dans une position veticale
- width: largeur du module
- imageMaxWidth: largeur maximale de l'image
- imageMaxHeight: hauteur maximale de l'image

# Support et aide
Toute aide peut-être demandé sur [le forum 4th Party Modules](http://forum.bugsounet.fr)

# Crédits:
 * Développeur:
   * @bugsounet
 * Licence: MIT
 
# Note @FranceTV
* Les couleurs, mise en forme ainsi que logo de `franceinfo:` sont utilisés dans ce module, sans accord préalable.
* Tous droits restent bien sûr en faveur de `FranceTV` et `franceinfo:`
* N'hesitez pas à me contacter, si cela pose réellement souci
