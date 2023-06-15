---
title: Radio_french
description: 
published: true
date: 2021-06-19T08:52:22.772Z
tags: 
editor: markdown
dateCreated: 2021-06-19T08:51:39.956Z
---

# Module Radio
<br>

## Un total de 15 radios ont été pré-configurés

- [Chérie FM](https://www.cheriefm.fr/)
- [RTL](https://www.rtl.fr/)
- [Rire Et Chansons](https://www.rireetchansons.fr/)
- [France Info](https://www.francetvinfo.fr/)
- [RTL2](https://www.6play.fr/rtl2)
- [Fun Radio](https://www.funradio.fr/)
- [Europe 1](https://www.europe1.fr/)
- [RFM](http://www.rfm.fr/)
- [RMC](https://rmc.bfmtv.com/)
- [NRJ](https://www.nrj.fr/)
- [Nostalgie](https://www.nostalgie.fr/)
- [Contact FM](https://www.mycontact.fr/)
- [Voltage](https://www.voltage.fr/)
- [Skyrock](https://skyrock.fm/)
- [Radio FG](https://www.radiofg.com/)

## Configuration

Afin de simplifier la configuration au maximum, un `recipe` a été créé.<br>
Il suffit simplement de l'ajouter à la configuration de `GoogleAssistant`<br>
Ce `recipe` se nomme: `ExtRadio_fr.js`<br>
Pour l'ajouter, editer la configuration de `MMM-GoogleAssistant` dans votre fichier config.js<br>
exemple:
```js
{
  module: "MMM-GoogleAssistant",
  ...
  config: {
    ...
    recipes: [ "ExtRadio_fr.js" ]
    ...
```
Dans le cas où vous avez déjà d'autres `recipes`:<br>
exemple:
```js
{
  module: "MMM-GoogleAssistant",
  ...
  config: {
    ...
    recipes: [ "ExtRadio_fr.js", "Un_autre_recipe.js" ]
    ...
```
## Activation par commande vocale

Une fois le `recipe` installé, il faudra bien sur redémarrer `MagicMirror`<br>
Activez votre assistant avec votre `keyword` préféré et dites par exemple:<br>
`Mets Chérie FM`<br>
L'assistant envoie les données nécessaires à `Extented Display` et se connectera à la radio demandé.<br>

## Notes:
* Le module Radio fonctionnera **uniquement en HTML5**.
* Si aucun son n'est produit mais le logo de la radio est affiché, il faudra vérifier votre sortie son par défaut et votre fichier `.asoundrc`
