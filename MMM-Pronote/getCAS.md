---
title: getCAS.js
description: 
published: true
date: 2021-07-14T18:56:41.823Z
tags: 
editor: markdown
dateCreated: 2021-07-14T18:56:35.078Z
---

# Utilisation du script `getCAS.js`

> Permet de déterminer `url` et le `CAS` de connexion (Béta)
{.is-info}


## Edition du fichier

```
var config = {
  latitude: 50.173057556152344,
  longitude: 4.095112323760986,
  codePostal: 59740,
  url: null // example de format: "https://0590206D.index-education.net/pronote"
}
```
 
* `latitude` et `longitude` de l’établissement scolaire (ou de la ville): [Ceci](https://www.coordonnees-gps.fr/) pourrait vous aider
* `codePostal` de l'établissement: code postal complet ou les 4 premiers chiffres du code postal ou encore 0 pour avoir l'ensemble des établissements de la région
* `url` de pronote: Au premier lancement laissez sur `null`, une fois l'url trouvé grâce au scan, ajoutez cette dernière selon l'établissement désiré

## Exemple et application

### Exemple d'application avec les coordonnées de la configuration par defaut

dans votre terminal
```
~$ cd ~/MagicMirror/modules/MMM-Pronote
~/MagicMirror/modules/MMM-Pronote$ node getCAS.js 
Liste URL:

url: https://0590206D.index-education.net/pronote
Etablissement: COLLEGE DE SOLREZIS
Code Postal: 59740
-----
Le cas de `https://0590206D.index-education.net/pronote` est hdf
```

dans cette exemple, il suffit reporter `url` et `cas` dans le fichier de configuration de MMM-Pronote (Accounts)

### Exemple de sortie ou il faut choisir l'établissement

dans ma configuration, j'ai demandé tous les établissements de ma région `codePostal: 0`

```
Liste URL:

url: https://0590083V.index-education.net/pronote
Etablissement: LYCEE POL. CAMILLE CLAUDEL
Code Postal: 59613
-----
url: http://185.167.130.30/pronote/
Etablissement: COLLEGE JOLIOT CURIE
Code Postal: 59612
-----
url: http://62.160.33.161/pronote/
Etablissement: COLLEGE LEO LAGRANGE
Code Postal: 59611
-----
url: http://185.167.130.110/
Etablissement: COLLEGE DENIS SAURAT
Code Postal: 59132
-----
url: http://62.160.116.121/
Etablissement: COLLEGE JEAN ROSTAND
Code Postal: 59177
-----
url: http://195.25.176.49/pronote/
Etablissement: COLLEGE RENAUD BARRAULT
Code Postal: 59440
-----
url: http://185.163.29.238/pronote/
Etablissement: LYCEE JESSE DE FOREST
Code Postal: 59363
-----
url: https://0590206D.index-education.net/pronote
Etablissement: COLLEGE DE SOLREZIS
Code Postal: 59740
-----
url: http://185.171.156.166/pronote/
Etablissement: LYCEE PROF. PIERRE ET MARIE CURIE
Code Postal: 59620
-----
url: https://0596694F.index-education.net/pronote
Etablissement: COLLEGE FELIX DEL MARLE
Code Postal: 59620
-----
url: https://0590055P.index-education.net/pronote
Etablissement: COLLEGE JENNEPIN
Code Postal: 59149
-----
url: 
Etablissement: COLLEGE SAINT EXUPERY
Code Postal: 59330
-----
url: http://185.171.156.198/pronote/
Etablissement: LYCEE PLACIDE COURTOY
Code Postal: 59618
-----
url: http://195.25.174.41/pronote/
Etablissement: COLLEGE RONSARD
Code Postal: 59330
-----
url: http://185.167.130.14/pronote/
Etablissement: COLLEGE LAVOISIER
Code Postal: 59680
-----
url: http://195.25.194.33/pronote/
Etablissement: COLLEGE JACQUES BREL
Code Postal: 59720
-----
url: https://0595884A.index-education.net/pronote
Etablissement: LYCEE ANDRE LURCAT
Code Postal: 59602
-----
url: http://194.2.186.105/pronote/
Etablissement: COLLEGE VAUBAN
Code Postal: 59602
-----
url: https://0590151U.index-education.net/pronote
Etablissement: COLLEGE COUTELLE
Code Postal: 59600
-----
url: http://109.26.139.102/pronote/
Etablissement: LYCEE PIERRE FOREST
Code Postal: 59600
-----
url: 
Etablissement: COLLEGE GUILLAUME BUDE
Code Postal: 59600
-----
url: http://195.25.176.25/pronote/
Etablissement: COLLEGE JULES VERNE DE L&#039;EPINETTE
Code Postal: 59600
-----
url: https://0590109Y.index-education.net/pronote
Etablissement: COLLEGE THOMAS
Code Postal: 59573
-----
url: http://194.2.175.217/pronote/
Etablissement: COLLEGE JEAN ZAY
Code Postal: 59606
-----
url: http://185.171.156.206/pronote/
Etablissement: L.P. LOUIS ARMAND
Code Postal: 59571
-----
url: http://185.180.246.14/pronote/
Etablissement: COLLEGE CHARLES DE GAULLE
Code Postal: 59460
-----

Merci de valider `url` correspondant à votre établissement dans votre configuration
et relancer le programme pour connaitre le `cas`
```

Je recherche le `COLLEGE DE SOLREZIS`, donc d’après la base de donnée `url` est `https://0590206D.index-education.net/pronote`

Afin de connaitre le cas du `COLLEGE DE SOLREZIS`, il suffit d’éditer le fichier de configuration de `getCAS.js` à nouveau<br>
Bien sur, ajouter le champ `url` de l'établissement voulu

```
var config = {
  url: "https://0590206D.index-education.net/pronote"
}
```
relancer le script avec votre configuration

```
~/MagicMirror/modules/MMM-Pronote$ node getCAS.js
Le cas de `https://0590206D.index-education.net/pronote` est hdf
```

> Vous avez donc votre `url` de connexion et votre `cas`
{.is-success}
