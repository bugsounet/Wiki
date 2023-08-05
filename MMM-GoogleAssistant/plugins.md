---
title: Plugins
description: 
published: true
date: 2023-08-05T09:44:25.889Z
tags: 
editor: markdown
dateCreated: 2022-03-14T23:10:57.003Z
---

 # plugins
`plugin` is some kind of `monkey patch` for external recipe or module to extend MMM-GoogleAssistant's program logic.

## example
You can do something on specific phase of MMM-AssistantGoogle module.
```js
plugins: {
  onReady: "DO_SOMETHING"
},

commands: {
  "DO_SOMETHING": {
    functionExec: ()=> {
      console.log("This will be executed when `onReady` phase.")
    }
  }
}
```

## plugins locations
```
onReady: ()=>{}
onNotificationReceived: (noti, payload)=>{}
onActivate: () => {}
onStatus: (status) => {}
```

## description of plugins
* `onReady`: with be executed when Assistant is ready (first Launch of GoogleAssistant)
* `onNotificationReceived`: will be executed on every notification received from other modules
* `onActivate`: will be executed when assistant is activated and can you can use the notification name and the payload of it
* `onStatus`: will be executed on each status change and you can use the status name (`status.actual`: actual status, `status.old`: last status)