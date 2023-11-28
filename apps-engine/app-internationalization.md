# App Internationalization

You can build your app in such a way that it can be adapted to different languages.

Here's what you need to do:&#x20;

* Create a folder named `i18n` at the root and create `.json` files with the abbreviation of each language you want your app to support. For example, `en.json`, `pt.json`. You can call the same file to translate the content across several app interactions.
* In the JSON files, provide the corresponding text in the chosen language against each key. This text is displayed on the UI.&#x20;
* Define the keys that you want to create translations for. You can add these keys for functions such as slash commands, UIKit elements, or app settings.

## Examples

The following points illustrate some examples to show how you can use app internationalization for your apps:

* While creating action buttons, in [#register-a-button](extend-app-capabilities/apps-engine-user-interface/action-buttons.md#register-a-button "mention"), we use the `labelI18n` parameter to name the action button with a key. Then in the [#add-localization](extend-app-capabilities/apps-engine-user-interface/action-buttons.md#add-localization "mention") section, we provide the value for this key which is displayed on the UI.
* `submit.send` is a key to send a message to the channel with values as shown below:&#x20;

{% code title="i18n/en.json" %}
```json
English
{
    "submit.send": "Send Message to Channel"
}
```
{% endcode %}

{% code title="i18n/pt.json" %}
```json
Portuguese
{
    "submit.send": "Enviar Mensagem para o Canal"
}
```
{% endcode %}

* The `i18n` folder of the [Jitsi app](https://github.com/RocketChat/Apps.Jitsi/tree/master/i18n) contains the keys and values for the supported languages.
