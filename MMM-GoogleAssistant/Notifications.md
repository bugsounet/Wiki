---
title: Notifications
description: 
published: true
date: 2023-08-05T09:43:21.514Z
tags: 
editor: markdown
dateCreated: 2022-03-14T22:37:03.255Z
---

# Notifications for developers
> For comunicate with other modules `MMM-GoogleAssistant` is ready with incoming and outgoing notification
{.is-success}


## Incoming notification
<br>

### **`GA_ACTIVATE`**
> With this notification, assistant will start listening your query
{.is-info}

```js
// In some module
this.sendNotification("GA_ACTIVATE")
```

### **`GA_FORCE_FULLSCREEN`**

> With this notification, you force fullscreen response of assistant
{.is-info}

```js
// In some module
this.sendNotification("GA_FORCE_FULLSCREEN")
```
### **`GA_STOP`**
> With this notification and when assistant speaking, you can force assistant to stop conversation and return to standby mode
{.is-info}

```js
// In some module
this.sendNotification("GA_STOP")
```

> Note: If you use a touch screen, you can touch the icon state to close conversation when assistant speaking ! 
{.is-success}


## Outgoing Notifications
* This module send ALL Status of the assistant
   * ASSISTANT_STANDBY
   * ASSISTANT_LISTEN
   * ASSISTANT_THINK
   * ASSISTANT_CONFIRMATION
   * ASSISTANT_REPLY
   * ASSISTANT_CONTINUE
   * ASSISTANT_HOOK
   * ASSISTANT_ERROR
