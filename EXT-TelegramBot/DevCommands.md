---
title: How to add commands
description: 
published: true
date: 2023-08-05T09:41:40.707Z
tags: 
editor: markdown
dateCreated: 2021-07-14T10:20:05.073Z
---

> TelegramBot is a bridge interface between user and module.
> So It is not so useful without supports of other modules.
> (See [What is available with TelegramBot]() and [Guide for design command]())
{.is-info}


Adding your command to TelegramBot is very easy.

# 1. Simplest 6 lines solution
Your module might already have some functions to execute.
```javascript
turnOnTV: function() {
  // your code for turning on TV
},
```

In this case, add below function in your module. It has just 6 line codes and it would cause no side-effect to your existing codes.

EXT_TELBOTCommands: function(commander) {
  commander.add({
    command: 'tvon',
    callback: 'turnOnTV'
  })
},
```

This makes your command `/tvon` to be added in TelegramBot.

Or you can just return your commands array instead of using `commander` object.

```javascript
EXT_TELBOTCommands: function(commander) {
  return [
    {
      command: 'tvon',
      callback: 'turnOnTV'
    }
  ]
},
```

Or you can add command on runtime dynamically through notification `EXT_TELBOT-REGISTER_COMMAND`
```js
// In your module.
this.sendNotification("EXT_TELBOT-REGISTER_COMMAND", {
 command: 'tvon',
 callback: 'turnOnTV'
})
```



> Don't use above methods together at same time. Your command will be registered twice.
{.is-warning}


When this command `/tvon` is called by the user in Telegram, your callback-function named `turnOnTV` will be executed.
It's really easy, isn't it?

`.EXT_TELBOTCommands()` function is used for getting available commands of your module. It might be also used for other Commander modules like voice assistants, web admins, sensors, buttons, or any other modules which want to command other modules if they supports.

> Wait! Some module has already registered the same command with mine, what happens? 
> 
> In that case, your `/tvon` will be changed to `/tvon0` or `/tvon1` or `/tvon2`, ... automatically. Don't worry. It depends on which modules user installed. And your callback-function or commands or arguments are never affected.
{.is-success}


# 2. Use `Notification`

Your module might be controllable by notification already.
```javascript
notificationReceived: function(notification, payload, sender) {
  if (notification == 'TURN_OFF_TV') {
    this.turnOffTV()
  }
},
```
In this case, even easier than 1.
```javascript
EXT_TELBOTCommands: function(commander) {
  commander.add({
    command: 'TURN_OFF_TV',
  })
},
```
When `callback` is omitted, TelegramBot send user's command `/TURN_OFF_TV` to your `.notificationReceived()` function as 'notification'.

# 3. Reaction
But these two methods are not so good because there is no reaction for the user. We can make your command to respond.
```javascript
EXT_TELBOTCommands: function(commander) {
  commander.add({
    command: 'tvon',
    callback: 'command_turnOnTV'
  })
},

command_turnOnTV: function(command, handler) {
  this.turnOnTV()
  handler.reply("TEXT", "Yes, Sir!")
},

turnOnTV: function() {
  // your code for turning on TV
},
```
When the user tries `/tvon`, `Yes, Sir!` will be responded on Telegram.

# 4. Arguments
Now, we will look the arguments. Each command could get arguments for detailed execution.
```javascript
EXT_TELBOTCommands: function(commander) {
  commander.add({
    command: 'tv',
    callback: 'command_turnTV'
  })
},

command_turnTV: function(command, handler) {
  console.log(handler.args)
},
```
If the user command `/tv` or `/tv blah blah blah`, your `handler.args` carries user inputs like these.
- `/tv` : `handler.args == null`
- `/tv blah blah blah` : `handler.args == 'blah blah blah'`
**You can parse this input by yourself, Or...**
```javascript
EXT_TELBOTCommands: function(commander) {
  commander.add({
    command: 'tv',
    callback: 'command_turnTV',
    args_pattern : ['on|off']
  })
},
```
You can use pre-defined pattern of arguements to catch them. Matched values would be result of `RegExp.exec()`.
- `/tv` : `handler.args == null` (This command is called without any additional parameter.)
- `/tv blah blah blah` : `handler.args == [null]` (This command is called with something, but not matched with your pattern array.)
- `/tv on` : `handler.args[0] == 'on'`
- `/tv offensive behavior is not good` : `handler.args[0] == 'off'` (well, maybe this is not your intend, anyway.)

```javascript
EXT_TELBOTCommands: function(commander) {
  commander.add({
    command: 'tv',
    callback: 'command_turnTV',
    args_pattern : [/on|off/, "/after:[0-9]+/"]
  })
},
```
`args_pattern` could be `RegExp` Object (`/[a-z]+/`), `RegExp like string` (`"/[a-z]+/"`) or just string (`"[a-z]+"`)
Anyway, like in this case, you can use multi patterns for catching arguments.
- `/tv` : `handler.args == null`
- `/tv blah blah blah` : `handler.args = [null, null]`
- `/tv test on` : `handler.args == ["on", null]`, `handler.args[0] == 'on'`, `handler.args[1] == null`
- `/tv what is after:10` : `handler.args == [null, "after:10"]`, `handler.args[0] == null`, `handler.args[1] == 'after:10'`
- `/tv blah after:5 blah on blah blah` : `handler.args == ["on", "after:5"]`

You can use `()` for grouping or catching complexed pattern. 
```javascript
EXT_TELBOTCommands: function(commander) {
  commander.add({
    command: 'tv',
    callback: 'command_turnTV',
    args_pattern : [/on|off/, "/after:([0-9]+)/"]
  })
},
```
- `/tv on blah blah after:10` : `handler.args[0] == 'on'`, `handler.args[1][0] == 'after:10'`, `handler.args[1][1] == '10'`

Well, the regular expression is always difficult to understand. You can give name your caught pattern for easy using.
```javascript
EXT_TELBOTCommands: function(commander) {
  commander.add({
    command: 'tv',
    callback: 'command_turnTV',
    args_pattern : [/on|off/, "/after:([0-9]+)/"],
    args_mapping : ["onoff", "time"]
  })
},
```
- `/tv after:10 on` : `handler.args['onoff'] == 'on'`, `handler.args['time'][1] == '10'`.

# 4-1. In `notification`
If you use `notificationReceived` instead of `callback`, only `handler.args` will be carried to `.notificationReceived()` as `payload`. `handler` itself is not carried. In this case, you cannot `react` because `handler` is not carried.

# 5. `callback: function(command, handler)`
Let's examine callback function.

`command` is string value of your command. You can control multi commands in one callback function with this parameter.
```javascript
EXT_TELBOTCommands: function(commander) {
  commander.add({
    command: 'tv',
    callback: 'command_home',
  })
  commander.add({
    command: 'radio',
    callback: 'command_home',
  })
},

command_home: function(command, handler) {
  if (command == 'tv') { ... }
},
```

`handler` object is the magic of this TelegramBot!

Usually, `handler` object has this structure. You can use these values for more detailed execution.
```javascript
TelegramBotMessageHandler = {
  chatId : number or string, // represents which chat room the command came from
  messageId : number or string, // id of this command message
  userId : number or string, // id of the user who sends this command.  
  sessionId : string, //if this message is the answer of previous .ask(), the seesionId which you've set for this dialog session will be shown here.
  
  message: [Object], // See below
  args : [Object], // See upper section 4.
  callbacks : [ask(), reply(), say()],
```
Details of `message` object:
```javascript
message = {
  admin: 'admin' or null, //if this message came from admin chat room by admin, this value would be 'admin'
  date : number (unix Timestamp), //time of message carried
  message_id : number or string,
  text : string, // whole text of message including command and arguments (e.g. '/tvon blah blah blah')
  chat : {
    id : number or string, //id of chat room
    username : string, //username of the owner who owns this chat room
    first_name : string, //first name of this owner
    last_name : string, //last name of this owner
  },
  from : {
    id : number or string, //id of user who sends this command
    username : string, //username of this sender who sends this command
    first_name : string, //first name of this sender
    last_name : string, //last name of this sender
    language_code : string //language code of this sender.
  },
}
```

And it has three reaction functions.
- `handler.reply()`
- `handler.say()`
- `handler.ask()`

See more detailed information : [[Guide for design command]]


# 6. Pour some sugar on me
You can add a short description of command for convenience. This description will be shown by `/help [command]`. You can use `markdown`.
```javascript
EXT_TELBOTCommands: function(commander) {
  commander.add({
    command: 'tvon',
    description: "You can turn on TV with this command.\nTry `/tvon`.",
    callback: 'turnOnTV'
  })
},
```

# 7. Some tips.
- To register your commands into Telegram's command hints. (When you type first `/`, the hint will be shown.)
  - For naming commands, use lower case letters. 
  - For description, First sentence or line-break should happen in 32 chars.
  - Then you can activate `/commands` with your TelegramBot and copy the result then go to `@BotFather` and feed it for `/setcommands`.

