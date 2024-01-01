---
title: 3. Configure: Google Action
description: 
published: true
date: 2024-01-01T14:14:35.200Z
tags: 
editor: markdown
dateCreated: 2023-08-06T10:57:43.868Z
---

> Let's Configure Google Actions
{.is-info}

# Select `overview`
![overview.png](/resources/smarthome/overview.png)

# Quick Setup
Select `Name your Smart Home action`

![quicksetup1.png](/resources/smarthome/quicksetup1.png) 

`Display Name` set it to `Jarvis`

![quicksetup2.png](/resources/smarthome/quicksetup2.png)

... and `Save`

# Select `Actions` on the left
![action6.png](/resources/smarthome/action6.png)

# `Fulfillment URL`
![fulfillment.png](/resources/smarthome/fulfillment.png)

**/!\ Replace `demo.bugsounet.fr` by your sub-domaine or dyn-dns address**

# Add capabilities
![capabilities.png](/resources/smarthome/capabilities.png)

check `Support local query`
... and `Save` it !

# Select `Account linking` on the left
![accountlinking.png](/resources/smarthome/accountlinking.png)

# `OAuth Client Information`
`Client ID issued by your Actions to Google`: enter your prefered Client login (as you wish) and **note it in your NotePad as `Client ID`**

`Client secret`: enter the password used in the config of `Gateway` (password field of the Gateway config)
`Authorization URL` and `Token URL`:

![oauth.png](/resources/smarthome/oauth.png)

**Replace `demo.bugsounet.fr` by your sub-domain or your dyndns address**

`Configure your client`:

![client1.png](/resources/smarthome/client1.png)

check this:

![client2.png](/resources/smarthome/client2.png) 

... And click `Next` and `Save`

# click on `Deploy`

![deploy.png](/resources/smarthome/deploy.png)

click on `Directory information`

![directoryinformation.png](/resources/smarthome/directoryinformation.png)

> Fill in the fields `Description`, `Images`, `contact details`, `Privacy and consent`.
{.is-warning}

> When done: `Save` it
{.is-success}

# click on `Company details` on the left

![compagnydetails.png](/resources/smarthome/compagnydetails.png)

> Fill in the fields too
{.is-warning}


# click on `Release`
> It's the last step!
{.is-success}


![release1.png](/resources/smarthome/release1.png)

![release2.png](/resources/smarthome/release2.png)

> Create a `new release`
> `Channel`: choose `alpha`
> `Release name`: keep by default
> and ... `Submit`
{.is-info}

![release3.png](/resources/smarthome/release3.png)

----

> **Google Action is now configured !**
{.is-success}
