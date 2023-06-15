---
title: MMM-SpeedTest
description: 
published: true
date: 2021-07-14T09:12:34.608Z
tags: 
editor: markdown
dateCreated: 2021-07-10T21:17:53.975Z
---

# MMM-SpeedTest

Bandwidth test from [speedtest.net](https://www.speedtest.net/) servers for MagicMirror

## Screenshoot
![](https://raw.githubusercontent.com/bugsounet/MMM-SpeedTest/master/installer/SpeedTest.png)

## Install

  ```sh
  cd ~/MagicMirror/modules
  git clone https://github.com/bugsounet/MMM-SpeedTest
  cd MMM-SpeedTest
  npm install
  ```
  
>   Installation time 30 min... Just open a Beer !
{.is-warning}


## Configuration

### Simple Sample

```js
    {
      module: 'MMM-SpeedTest',
      position: 'top_center',
      configDeepMerge: true
    },
```

### Personalized Sample

> This Configuration is the same like the Simple Configuration.
{.is-info}


If you want to tune it, you can change only the desired value

```js
    {
      module: 'MMM-SpeedTest',
      position: 'top_center',
      configDeepMerge: true,
      config: {
        debug: false,
        update: "1h",
        colored: true,
        download: {
          title: "Download Speed",
          scale: 100
        },
        upload: {
          display: true,
          title: "Upload Speed",
          scale: 100
        },
        ping: {
          display: true,
          title: "Ping",
          scale: 100
        },
        informations: true,
        server: {
          preferedId: null,
          acceptLicense: true,
          acceptGdpr: true
        }
      }
    },
```

### Configuration Structure

* Field in `root`

> |field | type | default | description
> |--- |--- |--- | ---
> |debug| BOOLEAN | `false` | enable or not debug mode
> |update| STRING | "1h" | Delay before next update in [h] [m] [s]  
> |colored| BOOLEAN | true | Use color for display ?
> |informations| BOOLEAN | true | Display informations from the test server 

* Field `download: {...}`

> |field | type | default | description
> |--- |--- |--- |---
> |title| STRING | "Download Speed" | You can change for your translation
> |scale| NUMBER | 100 | Max scale value for displaying (in Mbps)

* Field `upload: {...}`

> |field | type| default | description
> |--- |--- |--- |---
> |display| BOOLEAN | true | Display the result your Upload Speed
> |title| STRING | "Upload Speed" | You can change for your translation
> |scale| NUMBER | 100 | Max scale value for displaying (in Mbps)

* Field `ping: {...}`

> |field | type | default | description
> |--- |--- |--- |---
> |display| BOOLEAN | true | Display the result your ping value
> |title| STRING | "ping" | You can change for your translation
> |scale| NUMBER | 100 | Max scale value for displaying (in ms)

* Field `server: {...}`

> |field | type | default | description
> |--- |--- |--- |---
> |preferedId | NUMBER or NULL | null | ID of the server to restrict the tests against. NULL is a ramdom server
> |acceptLicense | BOOLEAN | true | Set to `true` to accept the Ookla EULA, TOS and Privacy policy. (You don't need to change it)
> |acceptGdpr| BOOLEAN | true | Set to `true` to accept the Ookla GDPR terms. (You don't need to change it)

> Notes:
>
>You can see the ID of the used server in name informations field on the mirror<br> Sample: In the screenshoot id is `24215` for ORANGE FRANCE.
{.is-info}


## Update

  ```sh
  cd ~/MagicMirror/modules/MMM-SpeedTest
  git pull && npm install
  ```


