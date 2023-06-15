---
title: EXT-SelfiesSender
description: 
published: true
date: 2023-03-28T14:57:19.389Z
tags: 
editor: markdown
dateCreated: 2022-11-23T18:59:17.146Z
---

> EXT-SelfiesSender is a plugins for sending your result selfies to Telegram, GooglePhotos or by mail.
{.is-info}

> This module an Extented plugin of `EXT-Selfies`
> It can't work by itself without this plugin
{.is-danger}

> This module can display any errors with `EXT-Alert` plugin
> For Sending any Photos to GooglePhotos, `EXT-GooglePhotos` is needed
{.is-warning}


# Installation

Clone the module into your MagicMirror module folder and execute `npm intall` in the modules directory.
```
cd ~/MagicMirror/modules
git clone https://github.com/bugsounet/EXT-SelfiesSender
cd EXT-SelfiesSender
npm install
```

# Configuration
> insert your configuration in the config.js file of MagicMirror.
{.is-info}

```js
{
  module: 'EXT-SelfiesSender',
  config: {
    debug: false,
    sendTelegramBotAuto: true,
    sendGooglePhotos: false,
    sendGooglePhotosAuto: false,
    sendMail: false,
    sendMailAuto: false,
    sendMailConfig: {
      transport: {
        host: 'smtp.mail.com',
        port: 465,
        secure: true,
        auth: {
          user: "youremail@mail.com",
          pass: "your mail password"
        }
      },
      message: {
        from: "EXT-SelfieSender <youremail@mail.com>",
        to: "who@where.com",
        subject: "EXT-SelfieSender -- This is your new selfie.",
        text: "New selfie."
      }
    }
  }
},
```

> | Options  | Descriptions | Type | Default |
> | ------- | --- | --- | --- |
> | debug | enable or not debug mode | Boolean | false |
> | sendTelegramBotAuto | Send to all admins the result of the selfie | Boolean | true |
> | sendGooglePhotos | Activate GooglePhotos and allow manual sending with TelegramBot | Boolean | false
> | sendGooglePhotosAuto | Send automaticaly all new selfies to GooglePhotos | Boolean | false
> | sendMail | Activate send mail and allow manual sending with TelegramBot | Boolean | false
> | sendMailAuto | Send automaticaly all new selfies by mail | Boolean | false
> | sendMailConfig | send mail configuration (see bellow) | Object |  |

# sendMailConfig Feature
> By seeing the default sample, there is 2 objects to configure inside:
{.is-info}

## transport
> | Options  | Descriptions | Type | Default |
> | ------- | --- | --- | --- |
> | host | host of your stmp server (google server will not works !) | String | null
> | port | port of email server (see your mail provider) | Number | 465 |
> | secure | Need to activate a secure connexion ? | Boolean | true
> | auth | Authentication to mail server (see bellow) | Object |  |

### auth
> | Options | Descriptions | Type
> | --- | --- | --- |
> | user | Your username to autenticate to the mail server | String
> | pass | Your password to autenticate to the mail server | String

## message
> | Options  | Descriptions | Type
> | ------- | --- | --- | --- |
> | from | Mail address of the sender | String
> | to | Recipient email address | String
> | subject | Subject of the message | String
> | text | Text of the message | String


> Just copy/past the sample config for less difficulty !
> Replace default value by your own value !
{.is-info}

> EXT-SelfiesSender is able to determinate if your sendMailConfig is correct or not
> EXT-Alert will inform if any error detected !
> Naturaly you can use Debug mode and console in terminal to correct your error
> EXT-SelfiesSender will says your error ;)
{.is-success}


# TelegramBot commands

 * `/selfie`: will take a selfie
 * `/lastselfie`: will display last selfie to telegramBot
 * `/lastselfie mail`: will send the last selfie by mail (if mail function activated in config) 
 * `/lastselfie screen`: will display the last selfie on the screen of MagicMirror
 * `/lastselfie gphotos`: will send the last selfie to `EXT-GooglePhotos` to upload it (if activated in config)
 * `/emptyselfie`: will erase all selfies of `EXT-Selfies` photos directory

# Update
> For updating this plugin try this command:
{.is-info}

```
cd ~/MagicMirror/modules/EXT-SelfiesSender
npm run update
```

# Support and Helping
New forum and support for all @bugsounet modules is now localized [there](https://forum.bugsounet.fr) !