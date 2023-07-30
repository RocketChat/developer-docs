# Internationalization

Internationalization, often abbreviated as i18n, is a crucial aspect of software development that ensures a product's usability across various languages and regions. This document provides a brief guide on how to implement internationalization in Rocket.Chat.

When developing for Rocket.Chat, you have the ability to add strings to our translation files which later will be translated into other languages by our community translators.

**Tools Used**: In Rocket.Chat, internationalization is implemented using the [TAP:i18n](https://github.com/TAPevents/tap-i18n) meteor package, and managing contributions from the translator's community is done using [lingohub](https://lingohub.com/).

### Adding Strings to the Translation Files

To have a string translated you will first need a `key` that would be the identifier of the string you want to be translated, for example, the string `This room is read only` should have the key as `room_is_read_only`. Please keep in mind that when naming a key spaces should be replaced with underscores (`_`) and it should be named in English, as is the language selected for Rocket.Chat's code. Finally, you will have the `key/value` pair will look like this: `"room_is_read_only": "This room is read only"`

You can also specify `placeholders`, that will allow you to change information on the string via parameters when calling the `i18n` method. A parameter will be surrounded by two double underscores (`__ __`), and it will look like this, `"Conversation_closed": "Conversation closed: __comment__."` where `__comment__` can be replaced by any string provided in the parameters.

After that, you will need to add this key to its respective `i18n.json` file under the [i18n](https://github.com/RocketChat/Rocket.Chat/tree/develop/apps/meteor/packages/rocketchat-i18n/i18n) folder.

When your pull request is merged, our contributors at `LingoHub` will be notified of the new string and start translating it.

### Using Translated Strings on the code

Now that you have added your strings to the translation files, is time to use them in the code!

When writing on a `.js` file you can use the global method `TAPi18n.__()`. Now depending on where you are calling this method from, it can have different parameters. If you call it from the back-end of Rocket.Chat you will have to specify a language (which you can normally grab from a user's object). The method will look like this, `TAPi18n.__('YOUR_KEY_HERE', {}, user.language)`. You can also pass parameters on the second argument to replace placeholders on the translated strings. Now if you are calling from the front end you can simply use `TAPi18n.__('YOUR_KEY_HERE', {})` that will translate the selected string to the user's current selected language.

If the selected key is not present in the respective `.i18n.json` file it will default it to English, if no key is found it will display the key inserted in the method as a string.

Now if you are in a `.html` file, you can simply surround the string with `{{ "{{_ " }}}}` for example `{{ "{{_ YOUR_KEY_HERE" }}}}`. It will work the same as the method mentioned above, only with the convenience of adding it directly to the `.html` file.

Sometimes you can find some methods that require an object with a `i18nLabel` or `i18nDescription`. In these cases you only need to insert the key of the string, the method will do the rest.
