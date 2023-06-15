---
title: MMM-Shom
description: 
published: true
date: 2022-02-28T22:08:59.929Z
tags: 
editor: markdown
dateCreated: 2021-07-11T15:24:46.628Z
---

Single module to display the tide widget of [SHOM](https://maree.shom.fr) website on MagicMirror
MMM-Shom est un module simple pour afficher le widget marée du site [SHOM](https://maree.shom.fr) sur MagicMirror

# Screenshot
![](https://maree.shom.fr/assets/small-widget-50f22ea146481fa2b3f58c633f2dc9c4.png)

![](https://maree.shom.fr/assets/big-widget-48d9d3f426dff3d58c1a4cdd672f2489.png)

# Installation

Pour installer ce module, essayez les commandes suivante:

```sh
cd ~/MagicMirror/modules/
git clone https://github.com/bugsounet/MMM-Shom
cd MMM-Shom
npm install
```

# Configuration

```js
{
  module: 'MMM-Shom',
  position: "top_center",
  configDeepMerge: true,
  config: {
    debug: false,
    scriptURL: "https://services.data.shom.fr/hdm/vignette/grande/BREST?locale=fr",
    update: 1000 * 60 * 60
  }
},
```

* debug: Active le mode debug
* scriptURL: URL proposé par le site de Shom
* update: temps avant mise à jour pour rafraîchir le widget (en ms)

# Comment avoir l'adresse de `scriptURL`

> Connectez-vous sur le site de [SHOM](https://maree.shom.fr)
{.is-info}

* Selectionnez `Générer une vignette`
* Recherchez `Le Nom du port`
* Selectionnez `Petite vignette` ou `Grande vignette`
* Générez une vignette
* le site de shom va vous proposer une partie de code comme ceci:<br>
`<script src="https://services.data.shom.fr/hdm/vignette/petite/BREST?locale=fr"></script>`<br>
scriptURL va etre dans ce cas: `"https://services.data.shom.fr/hdm/vignette/petite/BREST?locale=fr"`<br>

Il suffit donc de le reporter dans la configuration du module
```js
scriptURL: "https://services.data.shom.fr/hdm/vignette/petite/BREST?locale=fr",
```

# Merci !
* Groupe Français de Facebook: [Entraide Magic Mirror Raspberry Pi](https://www.facebook.com/groups/2832574870153883)
* Merci pour cette idée: `@Jo Roco` !
