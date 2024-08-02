---
title: Before First Start
description: 
published: true
date: 2024-08-02T06:36:12.310Z
tags: 
editor: markdown
dateCreated: 2022-03-14T17:53:00.620Z
---

# Before the First Launch of MMM-GoogleAssistant

Right,
 * You have done [Google Assistant Setup](/MMM-GoogleAssistant/SetupCredentials)
 * You have done your personal module configuration
 * You have installed minimum [Extented plugins](/MMM-GoogleAssistant/ExtentedPlugins#advice-to-start) needed

Now, let's generate Google Assistant token

```sh
cd ~/MagicMirror/modules/MMM-GoogleAssistant
npm run token
```
That will open the manager tools for create token, just repond `Y` for the `Google Assistant`

If you want to reinstall the Google Assistant SDK token, you can use again with this tools 

Sample:
```sh
pi@raspberrypi:~/MagicMirror/modules/MMM-GoogleAssistant $ npm run token

> MMM-GoogleAssistant@5.X.X token
> installer/token.sh

Welcome to MMM-GoogleAssistant Token generator!

Do you want to install/reinstall MMM-GoogleAssistant token? [Y/n] 
Your choice: y
Opening OAuth URL. Return here with your code.

If your browser will not open, you can copy/paste this URL:
 https://accounts.google.com/o/oauth2/v2/auth?....
Paste your code: MY_very_long_google_code_sended_by_google

[GA] Token created!

Done.
```

> Choice is waiting for [Y or N] and don't need [Enter] for confirm
> So: don't use [Y and enter], just use only [Y]
{.is-warning}


# Let's start it !

On start MMM-GoogleAssistant will check if your configuration is ready for using.<br>
If any error detected, MMM-GoogleAssistant will inform you
