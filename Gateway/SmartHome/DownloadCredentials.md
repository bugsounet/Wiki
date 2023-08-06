---
title: Download Credentials
description: 
published: true
date: 2023-08-06T13:40:42.116Z
tags: 
editor: markdown
dateCreated: 2023-08-06T13:27:12.253Z
---

> Your `credentials` is now reated, let's download it !
{.is-info}


# DownLoad `credentials`

## Go back again to `Credentials`

![credentials3.png](/resources/smarthome/credentials3.png)

## Select `Gateway` account in `Service Account` section
![credentials4.png](/resources/smarthome/credentials4.png)

## Select `KEYS`
![credentials5.png](/resources/smarthome/credentials5.png)

## Click on `ADD KEY` and select `Create new key`
![credentials6.png](/resources/smarthome/credentials6.png)

## `CREATE` the key in `JSON` format
![credentials7.png](/resources/smarthome/credentials7.png)

> **The file will be generated and the download will start automatically**
{.is-success}

# Copy credentials to `Gateway`

Rename the downloaded file to `credentials.json` and past it to `~/MagicMirror/modules/Gateway` directory

**Warn:** This `credentials` are **NOT** `MMM-GoogleAssistant` credentials !

## Verify `project_id` of `MMM-GoogleAssistant` and `SmarHome`

Run again this script:

```sh
cd ~/MagicMirror/modules/Gateway/
npm run project
```

> You **MUST** have same value on each credentials!
{.is-success}


```sh
Your MMM-GoogleAssistant project_id is: XXXXXX
---
Your SmartHome project_id is: XXXXXX
```

# Remove registration of `MMM-GoogleAssistant` from `GoogleHome app`

If you have an existing `Jarvis` in GoogleHome app: Let's delete it

```sh
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run delete
```

> Note: Don't worry, we will create it again later !
{.is-info}
