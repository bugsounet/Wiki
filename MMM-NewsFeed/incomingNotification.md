---
title: incoming Notification
description: 
published: true
date: 2022-06-12T13:53:04.888Z
tags: 
editor: markdown
dateCreated: 2021-06-22T17:48:01.020Z
---

Since v1.1.0, MMM-NewsFeed can be controled with Other Modules

* `NEWSFEED_DETAIL`: open the current news with `EXT-Browser` plugin
* `NEWSFEED_NEXT`: display the next news
* `NEWSFEED_PREVIOUS`: display the previous news
* `NEWSFEED_REFRESH`: force refresh all news data

Sample of sending notification with other module:

`this.sendNotification("NEWSFEED_DETAIL")`: for sending a request for open the curent news with `EXT-Browser` plugin

