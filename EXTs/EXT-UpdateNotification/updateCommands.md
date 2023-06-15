---
title: updateCommands
description: 
published: true
date: 2023-06-15T20:06:38.261Z
tags: 
editor: markdown
dateCreated: 2022-03-08T21:30:11.760Z
---

# `updateCommands: [],`

some modules have some personal command for updating

You can create personal commands for each wanted module

Sample:

```js
updateCommands: [
  {
    module: "MagicMirror",
    command: "rm package-lock.json && git reset --hard && git pull && npm install"
  },
  {
    module: "MMM-sampleModule",
    command: "git pull"
  },
  {
    module: "MMM-dummy",
    command: "git pull && npm install"
  }
],
```

> Notes: 
>
> by default, EXT-UpdateNotification will install other module with `git reset --hard && git pull && npm install` command
> It will check Errors of configuration
{.is-warning}

