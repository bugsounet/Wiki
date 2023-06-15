---
title: Configuration Structure
description: 
published: true
date: 2021-07-14T18:50:16.856Z
tags: 
editor: markdown
dateCreated: 2021-07-14T18:50:08.703Z
---

# Structure basique
```js
{
  module: "MMM-Pronote",
  position: "top_center",
  configDeepMerge: true,
  config: {
    debug: false,
    ...
  }
},
```

# Champs de configuration

## Champ `debug`
>|Champ | type | valeur par défaut
>|---|---|---
>|debug | BOOLEAN | false

Si vous définissez `debug` sur true `true`, les logs détaillé seront écrit en console. (généralement réservé aux développeurs)

## Champ `defaultAccount`
>|Champ | type | valeur par défaut
>|---|---|---
>|defaultAccount | NUMBER | 1

Défini le numéro du compte par défaut au démarrage de pronote  (d'apres Accounts: [])

## Champ `Accounts: []`
>|Champ | type | valeur par défaut
>|---|---|---
>|Accounts | ARRAY of OBJECT | [ {...},{...} ]
>|- url | STRING | null
>|- username | STRING | null
>|- password | STRING | null
>|- cas | STRING | none
>|- account | STRING | student
>|- studentNumber| NUMBER | 1

> Voir comment se connecter à [Pronote]
{.is-info}


## Champ `rotateAccount`
>|Champ | type | valeur par défaut
>|---|---|---
>|rotateAccount | BOOLEAN | true

en cas de multi-compte, effectue un changement de compte automatiquement à chaque `rotateInterval`

## Champ `rotateInterval`
>|Champ | type | valeur par défaut
>|---|---|---
>|rotateInterval | STRING | "1m"

Si multi-comptes, temps d'affichage des comptes. La valeur doit être exprimé en `h`, `m` et/ou `s` pour Heures, Minutes, Secondes.

## Champ `updateInterval`
>|Champ | type | valeur par défaut
>|---|---|---
>|updateInterval | STRING | "15m"

Delai de mises à jour automatique des comptes de `Pronote`. La valeur doit être exprimé en `h`, `m` et/ou `s` pour Heures, Minutes, Secondes.

## Champ `PeriodType`
>|Champ | type | valeur par défaut
>|---|---|---
>|PeriodType | STRING | "semester"

Permet de choisir la périodicité de votre établissement: `semester` pour semestre, `trimester` pour trimestre

## Champ `Header: {}`

> Information sur l'entete de Pronote
{.is-info}


>|Champ (-Sous champ) | type | valeur par défaut
>|---|---|---
>|Header |  OBJECT | { ... }
>|- displayEstablishmentName | BOOLEAN | true
>|- displayStudentName | BOOLEAN | true
>|- displayStudentClass | BOOLEAN | true
>|- displayAvatar | BOOLEAN | true

* `displayEstablishmentName`: Affiche le nom de l'établissement de l’élève avec le logo de Pronote.
* `displayStudentName`: Affiche le nom de l’élève.
* `displayStudentClass`: Affiche la classe de l’élève.
* `displayAvatar`: Affiche l'avatar de l’élève. (non disponible en mode parent)

## Champ `Timetables: {}`

> Informations sur l'emploi du temps
{.is-info}


>|Champ (-Sous champ) | type | valeur par défaut
>|---|---|---
>|Timetables |  OBJECT | { ... }
>|- displayActual | BOOLEAN | true
>|- displayNextDay | BOOLEAN | true
>|- displayTeacher | BOOLEAN | true
>|- displayRoom | BOOLEAN | true

* `displayActual`: Affiche l'emploi du temps du jour.
* `displayNextDay`: Affiche l'emploi du temps du prochain jour de classe.
* `displayTeacher`: Affiche le nom du professeur.
* `displayRoom`: Affiche le numéro ou le nom de la salle de cours.

### Champ `Averages: {}`

> Information sur les moyennes de l'élève
{.is-info}


>|Champ (-Sous champ) | type | valeur par défaut
>|---|---|---
>|Averages |  OBJECT | { ... }
>|- display | BOOLEAN | true
>|- displayStudent | BOOLEAN | true
|- displayClass | BOOLEAN | true

* `display`: Affiche la section de la moyenne de l’élève.
* `displayStudent`: Affiche la moyenne de l’élève.
* `displayClass`: Affiche la moyenne de la classe.
 
### Champ `Marks: {}`

> Information sur les notes de l'élève
{.is-info}


>|Champ (-Sous champ) | type | valeur par défaut
>|---|---|---
>|Marks |  OBJECT | { ... }
>|- display | BOOLEAN | true
>|- searchDays | NUMBER | 7
>|- displayAverage | BOOLEAN | true
>|- displayCoeff | BOOLEAN | true

* `display`: Affiche la section des note de l’élève.
* `searchDays`: Permet une recherche des notes obtenues sur un nombre de jours voulu (jusqu'au jour actuel). Par default: les 7 derniers jours 
* `displayAverage`: Affiche la moyenne de la matière.
* `displayCoeff`: Affiche le coefficient de la note.

### Champ `Homeworks: {}`

> Information sur les devoirs
{.is-info}


>|Champ (-Sous champ) | type | valeur par défaut
>|---|---|---
>|Homeworks |  OBJECT | { ... }
>|- display | BOOLEAN | true
>|- searchDays | NUMBER | 7
>|- numberDays | NUMBER | 1
>|- displayDescription | BOOLEAN | true
>|- displayDone | BOOLEAN | true

* `display`: Affiche les devoirs à faire.
* `searchDays`: Période de recherche pour les devoirs. Par défaut: les 7 prochains jours.
* `numberDays`: Affiche les devoirs sur le nombre de jours défini.
* `displayDescription`: Affiche la description du devoir à effectuer.
* `displayDone`: Indique les devoirs effectués.

### Champ `Absences: {}`

> Informations sur les absences
{.is-info}


>|Champ (-Sous champ) | type | valeur par défaut
>|---|---|---
>|Absences |  OBJECT | { ... }
>|- display | BOOLEAN | true
>|- searchDays | NUMBER | 7
>|- number| NUMBER | 1

* `display`: Affiche les absences.
* `searchDays`: Période de recherche pour les absences. Par défaut: les 7 derniers jours.
* `number`: Affiche uniquement les X dernières absences.

## Champ `Delays: {}`

> Informations sur les retards
{.is-info}


>|Champ (-Sous champ) | type | valeur par défaut
>|---|---|---
>|Delays |  OBJECT | { ... }
>|- display | BOOLEAN | true
>|- searchDays | NUMBER | 7
>|- number| NUMBER | 1

* `display`: Affiche les retards.
* `searchDays`: Période de recherche pour les retards. Par défaut: les 7 derniers jours.
* `number`: Affiche uniquement les X derniers retards.

## Champ `Holidays: {}`

> Informations sur les vacances
{.is-info}


>|Champ (-Sous champ) | type | valeur par défaut
>|---|---|---
>|Holidays |  OBJECT | { ... }
>|- display | BOOLEAN | true
>|- number| NUMBER | 3

* `display`: Affiche les prochaines vacances.
* `number`: Nombre de vacances a venir à afficher.

## Champ `ReplaceSubjects: []`

> Permet de changer le nom de la matière du cours en votre propre nomination.
{.is-info}

Exemple:
```js
          ReplaceSubjects: [
            { "SCIENCES VIE & TERRE" : "SVT" },
            { "ESPAGNOL LV2" : "ESPAGNOL" },
            { "MATHEMATIQUES" : "MATH" },
            { "ED.PHYSIQUE & SPORT." : "SPORT" }
          ],
```
* change l'affichage de `SCIENCES VIE & TERRE` en `SVT`
* change l'affichage de `"ESPAGNOL LV2` en `ESPAGNOL`
* change l'affichage de `MATHEMATIQUES` en `MATH`
* change l'affichage de `ED.PHYSIQUE & SPORT.` en `SPORT`

## Champ `Notifications: {}`

> active ou non les notifications sur telegramBot en cas de nouvelles informations
{.is-info}


>|Champ | type | valeur par défaut
>|---|---|---
>|absences | BOOLEAN | true
>|delays | BOOLEAN | true
>|average | BOOLEAN | true
>|marks | BOOLEAN | true
>|homeworks | BOOLEAN | true

* `absences`: Active les notifications si absences
* `delays`: Active les notifications si retards (non disponible actuellement, a venir...)
* `average`: Active les notifications si nouvelle moyennes
* `marks`: Active les notifications si nouvelle notes
* `homeworks`: Active les notifications si nouveau devoirs

## Champ `NPMCheck: {}`

> Ceci permet de vérifier les mise à jours des librairie NPM @bugsounet utilisées.
{.is-info}

MMM-Pronote utilise des librairies npm @bugsounet et malheureusement le module de notification par defaut n'est pas programmé pour afficher les mise a jours de mes librairies personnelles<br>
Vous pouvez utiliser le module `alert` pour afficher les mise à jours ou le nouveau module de notification [MMM-UpdateNotification](https://github.com/bugsounet/MMM-UpdateNotification) pour une mise a jour automatique

>|Champ | type | valeur par défaut
>|---|---|---
>|NPMCheck | OBJECT | { ... }
>|-useAlert | BOOLEAN | true

- useAlert: si défini sur `true`, le module utilisera le module `alert` pour vous avertir; si defini sur `false`, le module utilisera [MMM-UpdateNotification](https://github.com/bugsounet/MMM-UpdateNotification)

> MMM-UpdateNotification est pre-reglé pour faire les mise à jour automatiquement de MMM-Pronote !
{.is-warning}
