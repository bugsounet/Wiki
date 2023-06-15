---
title: MMM-Ecowatt
description: 
published: true
date: 2022-12-08T22:24:35.500Z
tags: 
editor: markdown
dateCreated: 2022-12-08T21:58:15.654Z
---

# MMM-Ecowatt
Ecowatt, votre météo de l’électricité pour une consommation responsable

## Screenshot

![](https://raw.githubusercontent.com/bugsounet/MMM-Ecowatt/dev/screenshot.png)

### Legende

* <span style="color:#02f0c6">Vert: </span>Pas d’alerte.

* <span style="color:#f2790f">Orange: </span> Système électrique tendu. Les écogestes sont les bienvenus.

* <span style="color:#e63946">Rouge: </span> Système électrique très tendu. Coupures inévitables si nous ne baissons pas notre consommation.

## Installation

```sh
cd ~/MagicMirror/modules
git clone https://github.com/bugsounet/MMM-Ecowatt
cd MMM-Ecowatt
npm install
```

## Pre-Require

Créé un compte sur [Data RTE](https://data.rte-france.com/)

* Dans `Toutes les catégories` > `Ecowatt` > cliquer sur `Découvrir l'API`
* Dans la nouvelle page: cliquer sur `Abonnez-vous à l'API`
  * `CRÉER UNE APPLICATION`
  *  Dans le Champ Nom: mettre `MagicMirror`
  * Type: choisir: `Web / Serveur`
  * Description mettre: `MMM-Ecowatt` et Valider :)
* Dans `Mes Applications`
  * Cliquer sur `MagicMirror`
  * Recupérer les identifiants (credentials) en cliquant sur : `Copier en base 64`
  * Le coller dans un document text afin de le coller dans la configuration

## Configuration

```js
{
  module: "MMM-Ecowatt",
  position: "top_center",
  config: {
    debug: false,
    credentials: "Mes_identifiants_en_base64",
    zoom: 100
  }
},
```

>|Champ | Type | Description | Valeur par défaut
>|---|---|---|---
>|debug | Boolean | Si vous définissez `debug` sur true `true`, les logs détaillés seront écrit en console. | false |
>|credentials | String | Votre identifiant codé en base64 | null |
>|zoom | Number | Zoom en % du module la valeur `100 `étant la taille normale | 100 |

## Mise à jour du module
Utilisez simplement cette commande
``` sh
cd ~/MagicMirror/modules/MMM-Ecowatt
npm run update
```

## Remerciements
 * `ELMAGO` du forum officiel de MagicMirror pour son idée

## Notes
 * Les données sont mise à jours automatiquement toutes les heures
 * La récupération des données est caprieuse ! (La RTE autorise de collecter les données, je pense, toutes les 5 mins)
 * Elle est limité a **une seule** intérrogation de données par minutes donc un systeme de cache a été mis en place afin minimiser les erreurs au démarrage (Erreur 729 - Trop de requete)