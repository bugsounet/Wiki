---
title: Guide for design command
description: 
published: true
date: 2023-06-15T20:05:46.746Z
tags: 
editor: markdown
dateCreated: 2021-07-14T10:28:00.176Z
---

## You cannot tell first
Because your module doesn't know which chat rooms are on the Telegram. You should acquire `id of chat` first to tell something to the user. You cannot assume chat_id. The chat rooms could be destroyed, newly created, or just `id` could be changed. Don't assume.
But if you want, you can get and store `chat id` from `MessageHandler`. But keep in mind, the `id` might be invalid in future or not.
Therefore, It's not so good practice to tell something to the user without commands. Just react after getting commands from the user.

However, for the admin, you can tell to admin whenever you want. Send notification to `MMM-TelegramBot`, it will be shown in chat room of admin. 
```javascript
this.sendNotification('EXT_TELBOT-TELL_ADMIN', "Temperature is too high...")
//Or
this.sendNotification('EXT_TELBOT-TELBOT_TELL_ADMIN', {
  type: "PHOTO_PATH",
  path: "...",
  option: { caption: "Picture" }
})
```

## Reaction with rich contents.
`handler.say()` and `handler.reply()` can carry rich contents. (In `hanlder.ask()`, only "TEXT" is available.)

Generally, you can use these methods like belows;
```javascript
handler.say("TYPE", required, options={})
handler.reply("TYPE", required, options={}) //.reply and .say are almost same
handler.ask("TYPE", required, options={}, sessionId, callbackForAnswer)
```

### TEXT
`handler.say('TEXT', text, options={})`
#### required
- `text`is string.
#### options
See for `options` : https://core.telegram.org/bots/api#sendmessage
#### example
```
handler.reply("TEXT", "*Yes, Sir!*/nYour command will be executed!", {parse_mode:'Markdown'})
```
The length of text should be under 4000. An overflowed text will be truncated. There is a common pitfall. When you use 'markdown' for decorating your text, Invalid markdown usage will cause an error. So you should use markdown carefully.

### LOCATION
`handler.say('LOCATION', required={}, options={})`
#### required
- `required.longitude` is string or float number of longitude
- `required.latitude` is string or float number of latitude
#### options
See for `options` : https://core.telegram.org/bots/api#sendlocation
#### example
```
var location = {
  longitude: 2.294694,
  lattitude: 48.858093
}
handler.reply("LOCATION", location)
```

### VENUE
`handler.say('VENUE', required={}, options={})`
#### required
- `required.longitude` is string or float number of longitude
- `required.latitude` is string or float number of latitude
- `required.title` is string of location
- `required.address` is string of address
#### options
See for `options` : https://core.telegram.org/bots/api#sendvenue
#### example
```
var location = {
  longitude: 2.294694,
  lattitude: 48.858093,
  title: "Eiffel Tower",
  address: "Champ de Mars, 5 Avenue Anatole France, 75007 Paris, France"
}
handler.reply("VENUE", location)
```

### CONTACT
`handler.say('CONTACT', required={}, options={})`
#### required
- `required.first_name` is string of name of contact
- `required.phone_number` is string of phone_number of contact
#### options
See for `options` : https://core.telegram.org/bots/api#sendcontact
#### example
```
var company_info = {
  first_name: "Volkswagen Frankfurt",
  phone_number: "+49 1111 1111 1111"
}
handler.reply("CONTACT", company_info)
```

### PHOTO_URL
`handler.say('PHOTO_URL', url, options={})`
#### required
- `url` is URL of external image resource. (on the internet)
#### options
See for `options` : https://core.telegram.org/bots/api#sendphoto
#### example
```
handler.reply("PHOTO_URL", "http://sample.com/sample.png", {caption:"Coolest Picture"})
```

### PHOTO_PATH
`handler.say('PHOTO_PATH', path, options={})`
#### required
- `path` is absolute path of internal image resource. (in your raspberry pi)
#### options
See for `options` : https://core.telegram.org/bots/api#sendphoto
#### example
```
handler.reply("PHOTO_PATH", "/home/pi/MagicMirror/public/sample.jpg", {caption:"Coolest Picture"})
```

### AUDIO_URL
`handler.say('AUDIO_URL', url, options={})`
#### required
- `url` is URL of external audio resource. (on the internet)
#### options
See for `options` : https://core.telegram.org/bots/api#sendaudio
But sometimes, the options like 'title' or 'performer' could not work as intend. I think this is the problem of  `Telegram Bot API` or `node-telegram-bot-api`
#### example
```
handler.reply("AUDIO_URL", "http://sample.com/sample.mp3")
```

### AUDIO_PATH
`handler.say('AUDIO_PATH', path, options={})`
#### required
- `path` is absolute path of internal audio file resource. (in your raspberry pi)
#### options
See for `options` : https://core.telegram.org/bots/api#sendaudio
But sometimes, the options like 'title' or 'performer' could not work as intend. I think this is the problem of  `Telegram Bot API` or `node-telegram-bot-api`
#### example
```
handler.reply("AUDIO_PATH", "/home/pi/MagicMirror/public/sample.mp3")
```

### You can also use these;
- `VIDEO_URL`
- `VIDEO_PATH`
- `VOICE_URL`
- `VOICE_PATH`
- `DOCUMENT_URL`
- `DOCUMENT_PATH`

Every `*_URL` requires `url` for the parameter, and every `*_PATH` requires `path` for the parameter.

For available options, See https://core.telegram.org/bots/api

In `.ask()`, you can use only `'TEXT'`. Question is text, isn't it? 

This module doesn't validate your parameters, so you should call these methods with fully validated parameters.

## `.reply()` and `.say()`
These two methods of `handler` are almost same. but `.reply()` will be attached to the specific message.(usually previous command of the user).
If TelegramBot is in group chat room, and several users are commanding now. People cannot distinguish your reactions without `reply`. When you use `reply` for the specific message, users can get a reaction for his command. 

You can store and reuse `handler` for later or for jobs long-time taken. At that case, You can also use `.reply()` for the proper response.

## Don't try to make dialog UX (avoid using `.ask()`)
Unlike your thought, dialog UX is very difficult to implement. Making dialog UX could be easier when you implement your own TelegramBot for 1on1 chat. But you should share this bot with other modules, and you cannot control the members who use this bot in real life. So there could be so many problems.
- **When Bot ask something... to whom?** : It means you should store and manage `chatId` and `userId` (and even `messageId`) by yourself. Of course, `MessageHandler` could automatically carry these values, and you can use those. However you should get the answer from the user, so...
- **Someone replied something... Is it right answer?** : You SHOULD check the replied message IS REAL ANSWER.<br>Assume your bot in many chat rooms simultaneously. Your bot SHOULD find the right message from so many messages of many chat rooms. If someone answers for your asking, but he is not the right person who your module had asked. And your target person might say something, but how do you know that is the answer for your asking?<br>Well, The user can also `reply` to your asking. `TelegramBot` automatically check user's reply and carry it to you directly. However, user's answer would not be a formal command. It could not be pre-defined, so this module just tosses whole message to your module to handle it by itself.
- **Bot is stupid, it has no memory** : 1on1 chat is very easy. But real-life usage is not that kind. When you ask something to a user, you SHOULD manage DIALOG SESSION per each dialog between the user and your module in each chat room. `.ask()` method supports `sessionId`. If some `answer` was replied from proper user(as TelegramBot thought), same `sessionId` which is used when you use `.ask()` will be carried. You should check that value and consider this message as answer of your previous question. Bot doesn't know when the dialog ends, so the once replied `sessionId` will be destroyed. It means if you need the additional or next step of the question, you should manage your `sessionId` by yourself.

Let's see an example.
```javascript
EXT_TELBOTCommands: function(commander) {
  commander.add({
    command: 'choice',
    callback: 'askFunc'
  })
},

askFunc : function(command, handler) {
  //if command == choice, it would be first ask, if command == ask_again, it would be re-ask
  var chatId = handler.message.chat.id
  var userId = handler.message.from.id
  var messageId = handler.message.message_id
  var userName = handler.message.from.username
  var sessionId = messageId + ":" + userId + ":" + chatId
  this.session[sessionId] = handler //you should manage session for answer
  var text = "Ok, @" + userName + ", What do you want? Please select 'on' or 'off'."

  handler.ask("TEXT", text, {}, sessionId, this.answerFunc.bind(this))
}
```
Hmmmm... It looks not so difficult, does it?

Just asking is easy. Getting answer is difficult.

```javascript
answerFunc: function(command, handler) {
    var chatId = handler.message.chat.id
    var userId = handler.message.from.id
    var messageId = handler.message.message_id
    var userName = handler.message.from.username
    var sessionId = messageId + ":" + userId + ":" + chatId

    var originalHandler
    if (handler.sessionId && typeof handler.reply_to_message !== 'undefined') {
      if(this.session.hasOwnProperty(handler.sessionId)) {
        originalHandler = this.session[handler.sessionId]
        if (originalHandler.message.message_id == handler.reply_to_message.message_id) {
          var text = "I've got your answer..."
          var youranswer = handler.message.text
          if (isAnswerOn(youranswer)) {
            doSomethingOn()
            text += "I do something on as your wish."
            handler.reply("TEXT", text)
          } else if (isAnswerOff(youranswer)) {
            doSomethingOff()
            text += "I do something off as your wish."
            handler.reply("TEXT", text)
          } else {
            text += "But, I cannot understand your answer. Can you reply once again?"
            handler.reply("TEXT", text)
            delete this.session[handler.sessionId]
            this.askFunc("ask_again", handler)
            return
          }
        } else {
          var text = "You should not answer this question! This question was not for you."
          handler.reply("TEXT", text)
          this.askFunc("ask_again", originalHandler)
          delete this.session[handler.sessionId]
        }
      } else {
        var text = "I can't remember the question itself. I doubt it's already answered or too old."
        handler.reply("TEXT", text)
        return
      }
    } else {
      var text = "It's weird. You can't arrive here."
      handler.reply("TEXT", text)
      return
    }

    delete this.session[handler.sessionId]
  }
})
```
This code is not real executable, but you can understand how it goes.

> **My Suggestion: Don't design Dialog! It is more difficult than your thought.**
{.is-warning}


