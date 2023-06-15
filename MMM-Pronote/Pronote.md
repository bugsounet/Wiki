---
title: Se connecter au Serveur de Pronote
description: 
published: true
date: 2021-10-11T15:48:51.357Z
tags: 
editor: markdown
dateCreated: 2021-07-14T18:54:21.161Z
---

Le serveur de Pronote a besoin d'informations pour se connecter:

 * L'adresse de connection de votre pronote `url`
 * Votre nom d'utilisateur `username`, de votre mot de passe `password`.
 * Votre Geocalisation pour se connecter `cas`
 * Votre Type de compte `account`
 * Si vous avez plusieures enfants dans cette établissement `studentNumber`

Détaillons ceci :) 

# Determination de `url` et `cas`

2 Méthode sont disponibles

## 1) Méthode avec le script [getCAS.js](/fr/MMM-Pronote/getCAS) (Béta)

## 2) Méthode manuelle

### `url`

L'adresse de connexion est l'adresse version PC de votre site de pronote.<br>
Il suffit de copier l'adresse de connexion et la coller dans le champ `url`

Example en image:

![](https://raw.githubusercontent.com/bugsounet/MMM-Pronote/master/screenshot/url.png)

dans cette exemple le champ url serait : `url = "https://0590083v.index-education.net/pronote/",`

### `cas`

Géo-Localisation afin d’accéder a pronote selon l'identifiant fourni par l’établissement scolaire selon votre région

Voici les `cas` possible:

Le CAS a renseigner dans la configuration.<br>
L'URL est votre url de connexion pour vous identifier via votre PC a titre informatif (ne pas la reporter dans la configuration, ceci n'est pas l'url de pronote !)

- Académie d'Orleans-Tours (CAS : ac-orleans-tours, URL : "ent.netocentre.fr")
- Académie de Besançon (CAS : ac-besancon, URL : "cas.eclat-bfc.fr")
- Académie de Bordeaux (CAS : ac-bordeaux, URL : "mon.lyceeconnecte.fr")
- Académie de Bordeaux 2 (CAS : ac-bordeaux2, URL : "ent2d.ac-bordeaux.fr")
- Académie de Caen (CAS : ac-caen, URL : "fip.itslearning.com")
- Académie de Clermont-Ferrand (CAS : ac-clermont, URL : "cas.ent.auvergnerhonealpes.fr")
- Académie de Dijon (CAS : ac-dijon, URL : "cas.eclat-bfc.fr")
- Académie de Grenoble (CAS : ac-grenoble, URL : "cas.ent.auvergnerhonealpes.fr")
- Académie de la Loire (CAS : cybercolleges42, URL : "cas.cybercolleges42.fr")
- Académie de Lille (CAS : ac-lille, URL : "cas.savoirsnumeriques62.fr")
- Académie de Lille (CAS : ac-lille2, URL : "teleservices.ac-lille.fr")
- Académie de Limoges (CAS : ac-limoges, URL : "mon.lyceeconnecte.fr")
- Académie de Lyon (CAS : ac-lyon, URL : "cas.ent.auvergnerhonealpes.fr)
- Académie de Marseille (CAS : atrium-sud, URL : "atrium-sud.fr")
- Académie de Montpellier (CAS : ac-montpellier, URL : "cas.mon-ent-occitanie.fr")
- Académie de Nancy-Metz (CAS : ac-nancy-metz, URL : "cas.monbureaunumerique.fr")
- Académie de Nantes (CAS : ac-nantes, URL : "cas3.e-lyco.fr")
- Académie de Poitiers (CAS : ac-poitiers, URL : "mon.lyceeconnecte.fr")
- Académie de Reims (CAS : ac-reims, URL : "cas.monbureaunumerique.fr")
- Académie de Rouen (Arsene76) (CAS : arsene76, URL : "cas.arsene76.fr")
- Académie de Rouen (CAS : ac-rouen, URL : "nero.l-educdenormandie.fr")
- Académie de Strasbourg (CAS : ac-strasbourg, URL : "cas.monbureaunumerique.fr")
- Académie de Toulouse (CAS : ac-toulouse, URL : "cas.mon-ent-occitanie.fr")
- Académie du Val-d'Oise (CAS : ac-valdoise, URL : "cas.moncollege.valdoise.fr")
- ENT "Agora 06" (Nice) (CAS : agora06, URL : "cas.agora06.fr")
- ENT "Haute-Garonne" (CAS : haute-garonne, URL : "cas.ecollege.haute-garonne.fr")
- ENT "Hauts-de-France" (CAS : hdf, URL : "enthdf.fr")
- ENT "La Classe" (Lyon) (CAS : laclasse, URL : "www.laclasse.com")
- ENT "Lycee Connecte" (Nouvelle-Aquitaine) (CAS : lyceeconnecte, URL : "mon.lyceeconnecte.fr")
- ENT "Seine-et-Marne" (CAS : seine-et-marne, URL : "ent77.seine-et-marne.fr")
- ENT "Somme" (CAS : somme, URL : "college.entsomme.fr")
- ENT "Portail Famille" (Orleans Tours) (CAS : portail-famille, URL : "seshat.ac-orleans-tours.fr:8443")
- ENT "Toutatice" (Rennes) (CAS : toutatice, URL : "www.toutatice.fr")
- ENT "Île de France" (CAS : iledefrance, URL : "ent.iledefrance.fr")
- ENT "Mon collège Essonne" (CAS : moncollege-essonne, URL : "www.moncollege-ent.essonne.fr")
- ENT "Paris Classe Numerique" (CAS : parisclassenumerique, URL : "ent.parisclassenumerique.fr")
- ENT "Lycee Jean Renoir Munich" (CAS : ljr-munich, URL : "cas.kosmoseducation.com")
- ENT "L'Eure en Normandie" (CAS : eure-normandie, URL : "cas.ent27.fr")  

  * A vous de définir le votre selon les identifiants fourni par l'académie ou l’établissement scolaire
  * Exemple: l'établissement m'a fourni des identifiants ENT et je me situe dans le Hauts-de-France<br>
dans ce cas la valeur `cas` sera `cas: "hdf",`
  * Il est possible que votre établissement vous donne directement l'adresse de Pronote sans passer par l'identification du portail académique<br>
dans ce cas, il suffit de définir votre `cas` avec la valeur: `cas: "none",`

# `username` et `password`

username : nom d'utilisateur fourni par l’académie ou l'établissement scolaire<br>
password : mot de passe fourni par l’académie ou l'établissement scolaire

# `account`

type de compte:

 * `parent` : si vous voulez utiliser le compte parent
 * `student`: si vous utilisez directement le compte de l'enfant 

# `studentNumber`

Uniquement si vous utiliser le compte parent et que vous avez plusieurs enfants.

Permet de définir l'affichage du compte de l'enfant désiré par défaut.

Malheureusement, cela fonctionne par numéro et non par prénom de l'enfant.

* Exemple:

Vous avez 2 enfants dans le même établissement: Bugsounet et Bugsounette 

En essayant de definir `studentNumber: 1,` si vous avez Bugsounet<br>
Dans ce cas: `studentNumber: 2,` sera Bugsounette<br>
(ou inversement ! à vous de tester !)

# Exemple de configuration en compte simple
```
    Account: 1,
    Accounts: [
      {
        url: "https://myurl.com/pronote",
        username: "mylogin",
        password: "mypassword",
        cas: "hdf",
        account: 'parent',
        studentNumber: 1, // only for parent account
      }
    ],
```

# Exemple de configuration en compte multiple
```
    Account: 1,
    Accounts: [
      {
        // compte numéro 1
        url: "https://myurl.com/pronote",
        username: "mylogin",
        password: "mypassword",
        cas: "hdf",
        account: 'parent',
        studentNumber: 1, // only for parent account
      },
      {
        // compte numéro 2
        url: "https://myurl.com/pronote",
        username: "mylogin",
        password: "mypassword",
        cas: "hdf",
        account: 'parent',
        studentNumber: 2, // only for parent account
      },
      {
        // compte numéro 3
        url: "https://myotherurl.com/pronote",
        username: "myotherlogin",
        password: "myotherpassword",
        cas: "hdf",
        account: 'parent',
        studentNumber: 1, // only for parent account
      },
    ],
```
Ceci est un exmple de configuration avec 3 enfants !
* compte numero 1 : le 1er enfant identifié à l'etablisement 1
* compte numero 2 : le 2ème enfant est dans le même établisement donc seul le `studentNumber` change
* compte numero 3 : le 3eme enfant dans un autre établisement

A Noter `Account: 1`: permet de définir le compte par defaut à afficher (ici le compte numéro 1)

# MMM-GoogleAssistant
Si vous utilisez [MMM-GoogleAssistant](http://wiki.bugsounet.fr/MMM-GoogleAssistant), un recipe a été créé afin de basculer de compte
  * Copier le fichier `with-Pronote.js` situé dans le repertoire `resources`
  * Placer ce dernier dans le repertoire `recipes` de MMM-GoogleAssistant
  * Ajoutez le a la configuration de vos recipes

Pour basculer de compte dite simplement apres voir activer l'assistant: `Pronote <numéro>`

# MMM-TelegramBot
Si vous utilisez [MMM-TelegramBot](http://wiki.bugsounet.fr/MMM-TelegramBot), une commande a été créé afin de basculer de compte

`/pronote compte <numéro du compte>`