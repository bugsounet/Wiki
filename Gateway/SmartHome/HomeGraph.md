---
title: HomeGraph configuration
description: 
published: true
date: 2023-08-06T12:46:22.487Z
tags: 
editor: markdown
dateCreated: 2023-08-06T12:46:22.487Z
---

> Let's configure `HomeGraph` for live update in Google Home App
{.is-info}


Enable HomeGraph API for your project in the [Cloud Platform Console](https://console.cloud.google.com/)

> **select the same project as Smarthome !**
{.is-warning}


# Enable `HomeGraph` API
Make the same process like [this](/MMM-GoogleAssistant/SetupCredentials#prepare-project-with-api)
and search `HomeGraph` and enable it 

# create `credentials`

Select `API & Services` -> `Credentials`

![a49aa5be-96a7-4d3f-9237-23f95d79e359-image.png](/assets/uploads/files/1680351247962-a49aa5be-96a7-4d3f-9237-23f95d79e359-image.png) 

`Create Credentials`

![20aef720-e9af-4772-a453-f3595db12471-image.png](/assets/uploads/files/1680351336467-20aef720-e9af-4772-a453-f3595db12471-image.png) 

Select `Service Account`

![9858e810-d638-4319-9aa6-afae24d42117-image.png](/assets/uploads/files/1680264784045-9858e810-d638-4319-9aa6-afae24d42117-image.png) 

## step 1:

![c0f0c99a-efbb-4606-985a-ca9c5c37cea8-image.png](/assets/uploads/files/1680264852803-c0f0c99a-efbb-4606-985a-ca9c5c37cea8-image.png) 

Service account name: `Gateway`
Service account ID : it's auto complete... don't touch it !
Service account description: `Gateway` 

And... `Create and continue`

## step 2:
![2c1d59a2-d39c-4082-a0df-c7eee68107eb-image.png](/assets/uploads/files/1680264968509-2c1d59a2-d39c-4082-a0df-c7eee68107eb-image.png)

Select a role and search `token`
> **Note: translate `token` into your language, for example `jeton` in french**
{.is-info}

and select `Service Account Token Creator`

![daefe031-16d5-43b5-999a-42439b428306-image.png](/assets/uploads/files/1680265081044-daefe031-16d5-43b5-999a-42439b428306-image.png) 

click on `Continue` and click `Done`