---
title: Configuration
description: 
published: true
date: 2021-07-14T19:01:04.695Z
tags: 
editor: markdown
dateCreated: 2021-07-14T18:41:49.079Z
---

> Pour ceci utilisez le fichier de configuration de MagicMirror `config.js` pour configurer MMM-Pronote
{.is-warning}


# Configuration Simple
```js
{
  module: "MMM-Pronote",
  position: "top_center",
  configDeepMerge: true,
  config: {
    debug: false,
    Accounts: [
      {
        url: null,
        username: null,
        password: null,
        cas: "none",
        account: "parent",
        studentNumber: 1, // only for parent account
      }
    ],
  }
},
```

# Configuration entière et détaillée (voir [Structure de la configuration](/fr/MMM-Pronote/ConfigurationStructure))

> Cette configuration est la configuration par défaut, si vous ne définissez aucune variable
> Il est inutile de copier entièrement cette configuration.
> Changez uniquement les valeurs désirées !
{.is-warning}


```js
{
  module: "MMM-Pronote",
  position: "top_center",
  configDeepMerge: true,
  config: {
    debug: false,
    defaultAccount: 1,
    Accounts: [
      {
        url: null,
        username: null,
        password: null,
        cas: "none",
        account: "student"
      },
      {
        url: null,
        username: null,
        password: null,
        cas: "none",
        account: "parent",
        studentNumber: 1, // only for parent account
      }
    ],
    rotateAccount: true,
    rotateInterval: "1m",
    updateInterval: "15m",
    PeriodType: "semester",
    Header: {
      displayEstablishmentName: true,
      displayStudentName: true,
      displayStudentClass: true,
      displayAvatar: true
    },
    Timetables: {
      displayActual: true,
      displayNextDay: true,
      displayTeacher: true,
      displayRoom: true
    },
    Averages: {
      display : true,
      displayStudent: true,
      displayClass: true
    },
    Marks: {
      display: true,
      searchDays: 7,
      displayAverage: true,
      displayCoeff: true
    },
    Homeworks: {
      display: true,
      searchDays: 7,
      numberDays: 1,
      displayDescription: true,
      displayDone: true
    },
    Absences: {
      display: true,
      searchDays: 7,
      number: 1
    },
    Delays: {
      display: true,
      searchDays: 7,
      number: 1
    },
    Holidays: {
      display: true,
      number: 3
    },
    ReplaceSubjects: [],
    Notifications: {
      absences: true,
      delays: true,
      average: true,
      marks: true,
      homeworks: true
    },
    NPMCheck: {
      useChecker: true,
      delay: "45m",
      useAlert: true
    }
  }
},