---
title: MMM-NotificationReceived
description: 
published: true
date: 2021-07-14T11:26:23.266Z
tags: 
editor: markdown
dateCreated: 2021-07-14T11:26:16.817Z
---

Simple module for developping.<br>
It allow to show notification send by modules.<br>
Notification is shown in dev console launched by `npm start dev`

## Installation

```sh
cd ~/MagicMirror/modules
git clone https://github.com/bugsounet/MMM-NotificationReceived
```

## Configuration

```js
  {
    module: "MMM-NotificationReceived",
    disabled: false,
    config: {
      notificationFrom : [ "clock", "calendar" ]
    }
  },
```
- `notificationFrom` is an array of modules for which you want to see notifications.
- If you want to disable the module, you can use `disabled: true,`

## Support and Helping
Support is now on [the 4th Party Modules Forum](http://forum.bugsounet.fr)
