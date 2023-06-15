---
title: Google Assistant Setup
description: 
published: true
date: 2022-03-15T00:19:03.385Z
tags: 
editor: markdown
dateCreated: 2022-03-15T00:18:04.959Z
---

----
# !! UNDER REFRESH !!
# !! WILL COMING SOON !!
----

**[Installation](/MMM-GoogleAssistantv4/Installation) Step is needed before this setup**

Last test: 2020/06/03

## Get Auth and credentials to make profile.
1. Create a project in the [Actions Console](https://console.actions.google.com/)


**Follow this step**
  - New Project
  ![](/resources/1.png)
  - Agree and Continue
  ![](/resources/1b.png)
  - Create project
  ![](/resources/1c.png)

2. After creation, Enable `Google Assistant API` for your project in the [Cloud Platform Console](https://console.cloud.google.com/)

**Follow this step**
  - Agree and Continue<br>
  ![](/resources/2.png)
  - Select your project and note your `Project ID` name<br>
  ![](/resources/2a.png)
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
  
3. Return to Actions Console and Follow this instructions to register a device model

  - You can use this URL https://console.actions.google.com/u/0/project/[yourprojectId]/deviceregistration/ (change [yourprojectId] to your own Project ID)<br>
  ![](/resources/3.png)
  - Register Model as TV<br>
  ![](/resources/3b.png)
  - Download credentials<br>
  ![](/resources/3c.png)
  - Optional (Maybe for a future version Of GoogleAssistant)<br>
  ![](/resources/3d.png)

  - If needed, you can find again your credentials from [Cloud Platform Console](https://console.cloud.google.com/) (Your Project > APIs & Services > Credentials)<br>
  ![](/resources/4b.png)
4. `OAuth Consent Screen` setup
  - Go to [Cloud Platform Console](https://console.cloud.google.com/), then navigate to `APIs & Services > OAuth Consent Screen`. At first, you'll be asked which user type would use your project. Just select `External`.<br>
  ![](/resources/4c.png)
  - Select you email adress<br>
  ![](/resources/4d.png)
  - Save it<br>
  ![](/resources/4e.png)

5. `publish` your application
  <br>
  - You need to publish your app, just click on `PUBLISH APP`<br>
  ![publishtesting.png](/resources/publishtesting.png)
  - Accept any conditions and the result will be `in production`<br>
  ![publishproduction.png](/resources/publishproduction.png)

6. you have download your credentials file (`client_secret_XXX.json` file) for OAuth and Carefully store it in `MMM-GoogleAssistant` directory and rename it to `credentials.json`

```sh
cd ~/MagicMirror/modules/MMM-GoogleAssistant
mv client_secret_XXX.json credentials.json
```
