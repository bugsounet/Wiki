---
title: Recipes
description: 
published: true
date: 2023-08-05T09:43:50.127Z
tags: 
editor: markdown
dateCreated: 2022-03-14T23:02:19.006Z
---

# Recipes

> `MMM-GoogleAssistant` is basically implementation of Google Assistant SDK, but not alternative or equivalent of Real Google Home device. This module is developed for the purpose of controlling MagicMirror.
{.is-info}


To control MagicMirror or Device(Raspberry PI, etc.), this module could have extended feature which is not supported by SDK itself. We call it as `recipe`. Each recipe would be mixture of `transcriptionHook`, `action`, `plugin`, `responseHook` and `command`.

- `transcriptionHook` : Hooking some pattern from your speech.
- `plugin` : Hooking procedure of this module on specific point.
- `responseHook` : Hooking some pattern from response (screen output) of Google Assistant
- `command` : Execution as a result of `transcriptionHook`, `action`, `plugin`, `responseHook`

## Recipe file
**`recipes/recipe.template.js`**
```js
var recipe = {
  transcriptionHooks: {
    // Describe your transcriptionHook here.
  },
  plugins: {
    // Describe your plugin here.
  },
  responseHooks: {
    // Describe your responseHook here.
  },
  commands: {
    // Describe your command here.
  },
}
exports.recipe = recipe // Don't remove this line.
```
Not all parts have to be needed. If you need only `transcriptionHooks` and `commands` be needed, Write just them.

Each recipe file should locate in `recipes` directory.

Then, you can configure your config.js
```js
recipes: [
  "some_recipe.js", "other_recipe.js", ...
],
```

see [My own recipe](/MMM-GoogleAssistant/Preparedrecipes#my-own-recipe)

## Prepared recipes
- `recipe.template.js` : template of recipe file
- `Reboot-Restart-Shutdown.js` : Vocal control for reboot, restart or shutdown your mirror
- ...

See [Prepared recipes](/MMM-GoogleAssistant/Preparedrecipes)