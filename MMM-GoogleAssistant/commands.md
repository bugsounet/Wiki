---
title: commands
description: 
published: true
date: 2023-03-12T10:07:18.481Z
tags: 
editor: markdown
dateCreated: 2022-03-14T23:14:24.095Z
---

 # commands
- `command` will be the main job of all Hooks (transcriptionHook, action, plugin, responseHook)

## Structure
```js
commands: {
  "COMMAND_1": {
    notificationExec: {
      notification: "EXT-Alert",
      payload: {type:"information", message:"This is a test." }
    }
  },
  ...
}
```

## commands types
- `notificationExec` : emitting notification.
  - `notification` : string || (param, from)=>{ return string}
  - `payload` : object || variables || (param, from)=> {return object or variable}
- `shellExec` : execution shell command or shell script. (e.g. python script for LED)
  - `exec` : string || (param, from)=>{ return string}
  - `options` : string || (param, from)=>{ return string}
- `moduleExec` : Accessing specific module(s) to control module directly,
  - `module` : string || Array of string || (param, from)=>{ return string or Array of string}
  - `exec` : (module, param, from)=>{}
- `soundExec` :
  - `chime` : string (open or close)
  - `sound` : string (your personal file)

## static and dynamic execution.
### Static example
```js
commands: {
  "COMMAND_1": {
    notificationExec: {
      notification: "EXT-Alert",
      payload: {type:"information", message:"This is a test." }
    }
  },
  ...
}
```

### Dynamic example (callback)
```js
commands: {
  "COMMAND_1": {
    notificationExec: {
      notification: (params, from)=> {
        if (from === "HOOK_1") {
          return "EXT-Alert"
        } else {
          return "SOME_NOTIFICATION"
        }
      }
      payload: (params, from)=> {
        ...
        return { ... }
      }
    }
  },
  ...
}
```
`from` would be the name/id of trigger. It could be derived from transcriptionHooks, responseHooks, actions, plugins.
`params` would be various result of each trigger. For example, `params` will be a result of regular expression matching when it came from `transcriptionHook` or `responseHook`.

## soundExec command

### `chime` play official google open / close beep

`chime: "open"` for open
`chime: "close"` for close

### `chime` play official google open / close app

`chime: "opening"` for simulate an opening app
`chime: "closing"` for simulate an closing app

### `sound` play your personal sound

`sound: "my_sound.mp3"`