---
title: Prepared recipes
description: 
published: true
date: 2023-06-16T09:11:31.565Z
tags: 
editor: markdown
dateCreated: 2022-03-14T23:17:06.353Z
---

# Overview
We have prepared several recipes.

- **Templates/Examples**
  - recipe.template.js (recipe template file)
- **MagicMirror system**
  - Reboot-Restart-Shutdown.js (restart, reboot or shutdown your mirror)  
- **Recipes for your preferred modules**
  - with-status.js (LED strip control with your own python script)
  - many other in `recipes` directory of MMM-GoogleAssistant

## Reboot-Restart-Shutdown.js

How it's works ?

By reading the [source](https://raw.githubusercontent.com/bugsounet/MMM-GoogleAssistant/master/recipes/Reboot-Restart-Shutdown.js) of this recipe,
You can see there is 3 commands,
each command have a pattern (aska what do you have to say to activate the command)

* For reboot your Pi
You have to say: `reboot please`

* For restart MagicMirror
You have to says: `restart please`
> This command is ONLY availabe if you use `pm2 app` for starting `MagicMirror`
{.is-warning}

* For shutdown your pi
You have to say: `shutdown please`


> Naturally, you can change `pattern` of each `transcriptionHooks` for better using in accord with your language
{.is-info}

## with-status.js

* How it's works ?
GA will send the status (stand-by, listen, ...) to your wanted file

```
/**  with-status.js **/
/**  send the status of assistant to a python script **/
/** For LED Strip for example **/
/**     @bugsounet       **/

var recipe = {
  commands: {
    "Status": {
      shellExec: {
        exec: (param) => {
            return "python /home/pi/myscript.py " + param.status.actual
        }
      }
    }
  },
  plugins: {
    onStatus: "Status"
  },
}

exports.recipe = recipe
```

I have defined in the `with-status.js` sample
to run this command : `python /home/pi/myscript.py Status_of_GA`

*  Status_of_GA can be :
   * listen
   * standby
   * confirmation
   * reply
   * error
   * hook
* You can change the name and the path of the script (I don't force it) and can be and bash script or other
* How load this recipe ?

in GA configuration, you have an recipe field

just add it :)

samples :

 * `recipes: [ "with-status.js" ],`
 
*  `recipes: [ "with-status.js", "with-other-recipes.js" ],` for some other recipe needed

# My own recipe

You have created your own recipe
Save it in `recipes` folder of `MMM-GoogleAssistant`

add it in the `recipes:[]` of the config

sample: You have save `My_ownRecipe.js`

```
recipes: [ "My_ownRecipe.js" ],
```

If you have already some recipes, just add it in the array

```
recipes: [
  "My_ownRecipe.js",
  "with-other-recipes.js"
],
```


