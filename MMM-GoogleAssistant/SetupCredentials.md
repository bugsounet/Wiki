---
title: Setup Credentials
description: 
published: true
date: 2023-04-15T10:25:05.493Z
tags: 
editor: markdown
dateCreated: 2022-03-21T18:53:33.316Z
---

> [Installation](/MMM-GoogleAssistant/Installation) Step is needed before this setup
{.is-warning}


> Last test: 2022/03/21
{.is-success}

# Create a project.

1. Use your current `gmail` mail address (same like your phone)

2. Connect to [Cloud Platform Console](https://console.cloud.google.com/)
  - Agree and Continue<br>
  ![](/resources/2.png)

3. Create new project

 - Open project manager<br>
 ![projectselect.png](/resources/projectselect.png)
 
 - Create new project<br>
 ![newproject.png](/resources/newproject.png)
 
 - Enter your project name and Create<br>
 ![projectname.png](/resources/projectname.png)
 
 - Your new project is now created !<br>
 ![createnotification.png](/resources/createnotification.png)

# Prepare Project with API

 Enable `Google Assistant API` for your project in the [Cloud Platform Console](https://console.cloud.google.com/)

**Follow this step**

  - In the left menu select `APIs & Services` and `Library`<br>
  ![](/resources/2b.png)
  - API Library search<br>
  ![](/resources/2c.png)
  - Google Asssitant API search<br>
  ![](/resources/2d.png)
  - Enable Google Assistant API<br>
  ![](/resources/2e.png)
  - Wait for activation<br>
  ![](/resources/2f.png)
  

> Make the same process with this APIs:
>  `Photos Library API` (needed if you use EXT-GooglePhotos)
{.is-warning}

# Prepare `OAuth Consent Screen` setup

  - Navigate to `APIs & Services > OAuth Consent Screen`. At first, you'll be asked which user type would use your project. Just select `External`.<br>
  ![](/resources/4c.png)
  - Enter the app name (MMM-GoogleAssistant) and select your email adress in user support email field<br>
  ![appinfo1.png](/resources/appinfo1.png)
  
  - Enter again your email adress for developer contact information<br>
  ![appinfo2.png](/resources/appinfo2.png)
  and save and continue
  
  - Next part (scope) nothing to do ... just `save and continue`<br>
  - Test users add again your own email address<br>
  ![appinfo3.png](/resources/appinfo3.png)
  and save and continue
  
  - Verify your OAuth consent screen and if all is ok `Back to Dashboard`
  
# Create Credentials

 - In the left menu select `credentials` and `Create Credentials`<br>

![createcredentials.png](/resources/createcredentials.png)

 - Select `OAuth client ID` from the menu<br>
![createcredentials2.png](/resources/createcredentials2.png)

- Select `Web application` from the `application type` menu<br>
![createcredentials3.png](/resources/createcredentials3.png)

- Enter the `Name` of the OAuth client (MMM-GoogleAssistant) and Authorized redirect URIs as `https://googleassistant.bugsounet.fr`<br>
![createcredentials4.png](/resources/createcredentials4.png)
and create :)

- Download the JSON file
save it (for backup), rename it to `credentials.json` and past it into `MMM-GoogleAssistant` directory 

# `publish` your application
- You need to publish your app, just click on `PUBLISH APP`<br>
![publishtesting.png](/resources/publishtesting.png)

- Accept any conditions and the result will be `in production`<br>
![publishproduction.png](/resources/publishproduction.png)

