---
title: Configure Google Actions
description: 
published: true
date: 2023-08-06T11:14:26.816Z
tags: 
editor: markdown
dateCreated: 2023-08-06T10:57:43.868Z
---

> Let's Configure Google Actions
{.is-info}


# Select `overview`
![a6719a67-f2b2-46ac-90c8-da0a2f196ad7-image.png](/assets/uploads/files/1680349595612-a6719a67-f2b2-46ac-90c8-da0a2f196ad7-image.png)  

# Quick Setup
Select `Name your Smart Home action`
![138376f5-57a2-4ce1-8489-bcbe19a378c4-image.png](/assets/uploads/files/1680349628894-138376f5-57a2-4ce1-8489-bcbe19a378c4-image.png) 

`Display Name` set it to `Jarvis`
![54ad3a27-b91a-46f4-bcb2-7d6afad3a7b2-image.png](/assets/uploads/files/1680349659655-54ad3a27-b91a-46f4-bcb2-7d6afad3a7b2-image.png) 
... and `Save`

# Select `Actions` on the left
![382374a3-ac53-45de-84f0-4d37070c4d86-image.png](/assets/uploads/files/1680349680496-382374a3-ac53-45de-84f0-4d37070c4d86-image.png) 

# `Fulfillment URL`
![2da84384-be7b-4bb6-bdd6-4d5be51aa78d-image.png](/assets/uploads/files/1680349727987-2da84384-be7b-4bb6-bdd6-4d5be51aa78d-image.png) 
**/!\ Replace `demo.bugsounet.fr` by your sub-domaine or dyn-dns address**

# Add capabilities
![13.png](/assets/uploads/files/1680349749633-13.png) 
check `Support local query`
... and `Save` it !

# Select `Account linking` on the left
![ed271af1-da43-4a50-a778-05311bcd0e0c-image.png](/assets/uploads/files/1680349835644-ed271af1-da43-4a50-a778-05311bcd0e0c-image.png) 

# `OAuth Client Information`
`Client ID issued by your Actions to Google`: enter your prefered Client login (as you wish) and **note it in your NotePad as `Client ID`**
`Client secret`: enter the password used in the config of `Gateway` (password field of the Gateway config)
`Authorization URL` and `Token URL`:
![efe44330-8fde-4eb2-a755-9e3c973b7369-image.png](/assets/uploads/files/1680349855839-efe44330-8fde-4eb2-a755-9e3c973b7369-image.png) 

**Replace `demo.bugsounet.fr` by your sub-domain or your dyndns address**

`Configure your client`:
![35c6cbd8-d590-42a5-ae8d-b7751131b029-image.png](/assets/uploads/files/1680349873850-35c6cbd8-d590-42a5-ae8d-b7751131b029-image.png) 
check this:
![ca8274a0-3660-4d5e-8268-d928b6ffbc6a-image.png](/assets/uploads/files/1680349973712-ca8274a0-3660-4d5e-8268-d928b6ffbc6a-image.png) 
... And click `Next` and `Save`
# click on `Deploy`
![1166f304-6c28-4725-b63a-836698e68f77-image.png](/assets/uploads/files/1680350002837-1166f304-6c28-4725-b63a-836698e68f77-image.png) 
click on `Directory information`
![a739b4a6-a4ad-48f5-bf45-539dc9cb1781-image.png](/assets/uploads/files/1680350022717-a739b4a6-a4ad-48f5-bf45-539dc9cb1781-image.png) 
Fill in the fields `Description`, `Images`, `contact details`, `Privacy and consent`.
When done: `Save` it
# click on `Company details` on the left
![953ceffc-9f44-45a5-b965-0159614d37a4-image.png](/assets/uploads/files/1680350049016-953ceffc-9f44-45a5-b965-0159614d37a4-image.png) 
Fill in the fields too

# click on `Release` the last step !
![305f79d5-413c-4b27-ae95-d155f17a1043-image.png](/assets/uploads/files/1680350061452-305f79d5-413c-4b27-ae95-d155f17a1043-image.png)  

![f2906ae5-5618-4c3a-a352-c8560f11005e-image.png](/assets/uploads/files/1680350076317-f2906ae5-5618-4c3a-a352-c8560f11005e-image.png) 
Create a `new release`
`Channel`: choose `alpha`
`Release name`: keep by default
and ... `Submit`
![1a5802c3-f016-4b16-b298-7fab1ce12fed-image.png](/assets/uploads/files/1680350089411-1a5802c3-f016-4b16-b298-7fab1ce12fed-image.png) 

----

> **Google Action is now configured !**
{.is-success}
