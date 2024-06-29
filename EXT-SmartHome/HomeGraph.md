---
title: 5. Configure: HomeGraph
description: 
published: true
date: 2024-01-01T14:24:55.191Z
tags: 
editor: markdown
dateCreated: 2024-01-01T14:24:55.191Z
---

> Let's configure `HomeGraph` for live update in Google Home App
{.is-info}


Enable HomeGraph API for your project in the [Cloud Platform Console](https://console.cloud.google.com/)

> **select the same project as Smarthome !**
{.is-warning}


# Enable `HomeGraph` API
> Make the same process like [this](/MMM-GoogleAssistant/SetupCredentials#prepare-project-with-api)
> and search `HomeGraph` and enable it 
{.is-info}


# create `credentials`

Select `API & Services` -> `Credentials`

![credentials1.png](/resources/smarthome/credentials1.png)

`Create Credentials`

![credentials2.png](/resources/smarthome/credentials2.png)

Select `Service Account`

![serviceaccount.png](/resources/smarthome/serviceaccount.png)

## Step 1:

![serviceaccount1.png](/resources/smarthome/serviceaccount1.png)

Service account name: `Gateway`
Service account ID : it's auto complete... don't touch it !
Service account description: `Gateway` 

And... `Create and continue`

## Step 2:

![serviceaccount2.png](/resources/smarthome/serviceaccount2.png)

`Select a role` and search `token`
> **Note: translate `token` into your language, for example `jeton` in french**
{.is-info}

and select `Service Account Token Creator`

![serviceaccount3.png](/resources/smarthome/serviceaccount3.png)

click on `Continue` and click `Done`