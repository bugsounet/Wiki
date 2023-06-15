---
title: MMM-FreeBox4G
description: 
published: true
date: 2021-07-10T22:10:14.714Z
tags: 
editor: markdown
dateCreated: 2021-07-10T22:10:07.288Z
---

MMM-Freebox est un module pour le projet [MagicMirror](https://github.com/MichMich/MagicMirror) par [Michael Teeuw](https://github.com/MichMich).

Il permet d'afficher, sur votre Mirroir, divers informations de votre `Box 4G+` de [Free Mobile](http://mobile.free.fr/la-box-4G.html) en temps réel.

Plusieurs modules sont disponibles et permet l'affichage suivant:

 * Information Signal Réseau.
 * Appareils connectés
 * Débit utilisé par l'ensenble des appareils connectés
 * Consomation Download et Upload
 * Forfait restant

# Update
 * v1.0.0 (11/10/2020)
   * Initial Release

# Screenshot
![](https://raw.githubusercontent.com/bugsounet/MMM-FreeBox4G/dev/resources/FreeBox4G.png)

# Installation
 * Ce module utilise les nouvelles libraries de MagicMirror
 * Il est donc compatible à partir de MagicMirror v2.13.0
 * Clonez le module dans votre dossier de module de MagicMirror et exécutez `npm install` dans le répertoire du module.
```sh
cd ~/MagicMirror/modules
git clone https://github.com/bugsounet/MMM-FreeBox4G
cd MMM-FreeBox4G
npm install
```
# Configuration
Pour afficher le module, inserez ceci dans votre ficher `config.js`

## Configuration Minimale

```js
{
  module: "MMM-FreeBox4G",
  position: "top_center",
  configDeepMerge: true,
  config: {
    debug: false
  }
},
```

## Configuration Personalisée
Ceci est la configuration par defaut si vous definissez aucune valeurs

```js
{
  module: 'MMM-FreeBox4G',
  position: 'top_center',
  configDeepMerge: true,
  config: {
    debug: false,
    updateInterval: "5s",
    router: {
      ip: "192.168.8.1",
      password: "admin"
    },
    display: {
      Signal: true,
      Icon: true,
      Client: true,
      ClientIP: false,
      ClientType: true,
      Button: true,
      Rate: true,
      Conso: false,
      Used: true,
      activeOnly: false,
      sortBy: "device",
      textWidth: 250,
    },
    text: {
      reseau: "Réseau",
      debit: "Débit Actuel:",
      conso: "Consomation Actuel:",
      used: "Consomation Total:"
    },
    clients: [],
    excludeMac: []
  }
},
```
# Champ `root`

> | Option  | Description | Type | Defaut |
> | ------- | --- | --- | --- |
> | debug | Active le mode de debuguage | Boolean | false |
> | updateInterval | Delai de mise à jour en secondes | String | "5s" (5 sec) |

# Champ `router: {}`

> | Champ (- Option)  | Description | Type | Defaut |
> | ------- | --- | --- | --- |
> | router | Object | {...} |
> | - ip | Adresse ip de la Box 4G | String | "192.168.8.1" |
> | - password | Mot de passe de connexion a l'interface de la Box 4G | String | "admin" |

# Champ `display: {}`

> | Champ (- Option) | Description | Type | Defaut |
> | ------- | --- | --- | --- |
> | display | Object | {...} |
> | - Signal | Affiche les informations du reseau | Boolean | true |
> | - Icon| Affiche les icones | Boolean | true |
> | - Client | Affiche la liste des appareils | Boolean | true |
> | - ClientIP | Affiche l'addresse IPv4 de l'appareil | Boolean | false |
> | - ClientType | Affiche l'icone du type de connexion des appareils | Boolean | true |
> | - Button | Affiche les boutons de status de connexion | Boolean | true |
> | - Rate | Affiche le débit actuellement utilisé | Boolean | true |
> | - Conso | Affiche le detail de la consomation du mois | Boolean | false |
> | - Used | Affiche la consomation utilisé selon le forfait | Boolean | true |
> | - activeOnly | Affiche uniquement les appareils connectés | Boolean | false |
> | - sortBy | Classement des appareils connectés par: device, name ou mac| String | "device" |
> | - textWidth | Largeur du texte à afficher | Number | 250 |

# Champ `clients: []`

> Le champs client est un `Array`
{.is-warning}


> Permet de personaliser l'affichage du nom de l'appareil et son icone associé
{.is-info}


> | Champ | Description | Type |
> | ------- | --- | --- |
> | mac | Adresse Mac de l'appareil | String |
> | name | Persoanlise le nom de l'appareil | String |
> | device | Choix de l'icone de l'appareil | String |

## Icone pour device:

| Icone | Nom |
| --- | --- |
| ![](https://raw.githubusercontent.com/bugsounet/MMM-FreeBox4G/dev/resources/desktop1.png) | `desktop` |
| ![](https://raw.githubusercontent.com/bugsounet/MMM-FreeBox4G/dev/resources/laptop1.png) | `laptop` | 
| ![](https://raw.githubusercontent.com/bugsounet/MMM-FreeBox4G/dev/resources/mobile1.png) | `smartphone` |
| ![](https://raw.githubusercontent.com/bugsounet/MMM-FreeBox4G/dev/resources/tab1.png) | `tablet` |
| ![](https://raw.githubusercontent.com/bugsounet/MMM-FreeBox4G/dev/resources/printer1.png) | `printer` |
| ![](https://raw.githubusercontent.com/bugsounet/MMM-FreeBox4G/dev/resources/game1.png) | `console` |
| ![](https://raw.githubusercontent.com/bugsounet/MMM-FreeBox4G/dev/resources/tv1.png) | `television` |
| ![](https://raw.githubusercontent.com/bugsounet/MMM-FreeBox4G/dev/resources/nas1.png) | `nas` |
| ![](https://raw.githubusercontent.com/bugsounet/MMM-FreeBox4G/dev/resources/camera1.png) | `camera` |
| ![](https://raw.githubusercontent.com/bugsounet/MMM-FreeBox4G/dev/resources/router1.png) | `router` |
| ![](https://raw.githubusercontent.com/bugsounet/MMM-FreeBox4G/dev/resources/media1.png) | `multimedia` |
| ![](https://raw.githubusercontent.com/bugsounet/MMM-FreeBox4G/dev/resources/hub1.png) | `other` |

## Exemple
```js
clients: [
  {
    mac: "2C:54:91:35:AA:BB",
    name: "Xbox One"
    device: "console"
   },
   { 
     mac: "58:00:E3:0E:AA:BB",
     name: "TV",
     device: "television",
    },
    {
      mac: "98:DE:D0:0D:AA:BB",
      device: "desktop"
    },
],
```

# Champ `excludeMac: []`

> excludeMac est un `Array`
{.is-warning}


> Permet de ne pas afficher les appareils connectés avec certaines adresses MAC
{.is-info}


## Exemple

```js
excludeMac: [ "DC:A6:32:37:AA:BB", "B8:27:EB:00:CC:DD"]
```

