---
title: 4. Configure: your CLIENT_ID
description: 
published: true
date: 2023-08-07T08:21:11.510Z
tags: 
editor: markdown
dateCreated: 2023-08-06T12:37:53.241Z
---

# It's time to reopen your note pad !

You have 2 values: 
  * the first is the `project_id`
  * the second is the Client ID

Open the config of MagicMirror and find `Gateway` config field
Your must have a field named `CLIENT_ID`

By default `CLIENT_ID` is null
Replace `null` value by your own value of `Client ID` of the note pad

Sample:

```
CLIENT_ID: "mypreferedlogin",
```

> Don't forget to save your new configuration!
{.is-info}