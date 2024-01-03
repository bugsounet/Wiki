---
title: 0. Migrate from Gateway to MMM-GoogleAssistant v6
description: 
published: true
date: 2024-01-03T01:50:42.830Z
tags: 
editor: markdown
dateCreated: 2024-01-03T01:50:42.830Z
---

# Migrate to MMM-GoogleAssistant v6

> If you don't use smarthome functionality with Gateway:
> This is not necessary in your case
{.is-danger}

Good news !
I created a script that allows me to migrate all the necessary data from Gateway to MMM-GoogleAssistant

> This script will copy credentials, tokens to MMM-GoogleAssistant directory and purpose new MMM-GoogleAssistant Configuration
{.is-info}


Just try:
```sh
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run migrate
```

```sh
> MMM-GoogleAssistant@6.0.0 migrate
> node installer/migrate.js

~MMM-GoogleAssistant~ Migrate smarthome from v5 to v6~
~~This script is only need if you use Gateway and SmartHome fonctionality with MMM-GoogleAssistant v5~~

[GA] Detected Gateway v3.7.2 rev: 231206
[GA] Detected Gateway credentials.json file
[GA] Copy credentials from Gateway to MMM-GoogleAssistant
[GA] New credentials smarthome.json was copied to MMM-GoogleAssistant folder
[GA] Copy any tokens from Gateway to MMM-GoogleAssistant
[GA] All smarthome tokens was copied to MMM-GoogleAssistant/website/tokens folder
[GA] Check config.js file of MagicMirror
[GA] Found Gateway config: {
  username: 'admin',
  password: 'mypassword',
  CLIENT_ID: 'myclientID'
}
[GA] This is your new config of MMM-GoogleAssistant for using smarthome:

{
  module: 'MMM-GoogleAssistant',
  disabled: false,
  configDeepMerge: true,
  config: {
    debug: false,
    assistantConfig: {
      lang: 'en-US'
    },
    website: {
      username: 'admin',
      password: 'mypassword',
      CLIENT_ID: 'myclientID'
    }
  }
}

Happy use!
```

> All needed data has been copied !
{.is-success}

> Now, Let's copy your new configuration in your config.js file
> And restart MagicMirror²
> Check your Google Home app: `Jarvis` will be again in life ;)
{.is-info}

> Note: The other installation steps do not need to be done
{.is-warning}

