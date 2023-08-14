# Custom Themes

To customize the Rocket.Chat UI you can either modify the `rocketchat-theme` or `rocketchat-ui` packages directly.If you want to avoid conflicts with active development, it is recommended to create your own theme package.

### Creating a Theme

To add theme customizations to Rocket.Chat, you can create a Meteor package with your code and add it to the package file. If you want to share your theme with others, you can publish it as a public Meteor package outside the Rocket.Chat repo. Private themes would need to be maintained on your own fork of Rocket.Chat

&#x20;The minimum contents for a theme package is a `package.js` file containing the description below:

```javascript
Package.describe({
    name: 'author:mytheme',
    version: '0.0.1',
    summary: 'My theme customisations.',
    git: 'https://github.com/author/my-rocket.chat-theme'
});
```

Then, include dependent packages and your custom theme files like this:

```javascript
Package.onUse(function(api) {
    api.versionsFrom('1.2');
    api.use([
        'templating',
        'rocketchat:lib',
        'rocketchat:theme'
    ]);
    api.use('templating', 'client');
```

### Adding Stylesheets

The `rocketchat-theme` package provides methods for including [Less](https://lesscss.org/) asset files in the build. To use these methods, first include the _Less files_ and the server.coffee or server.js file to load them in the `package.js` manifest (within the `Package.onUse` function).

```javascript
    api.addAssets([
        'assets/theme.less'
    ], 'server');
    api.addFiles([
        'server.coffee'
    ], 'server');
```

Then, in `server.coffee` file,&#x20;

```javascript
RocketChat.theme.addPackageAsset -> Assets.getText 'assets/theme.less'
```

That will read in any styles and variables from your custom less file and compile it with the rest of the CSS.

### Adding and Modifying Templates

Here's an example of replacing the unauthorized page template:

An effective method to add your own templates and helpers is by utilizing the `'aldeed:template-extension`' package. Simply include it in your main package file.&#x20;

* In your package's manifest,  declare use of the `template-extension` package.&#x20;
* Next, add your template files into Meteor using the command `api.addFiles([myfiles], 'client')`.

Here's an example of replacing the unauthorized page template:

**In `package.js`**

```javascript
    api.addFiles(['views/notAuthorized.html', 'client.coffee'], 'client');
```

**In `views/notAuthorized.html`**

```markup
<template name="myNotAuthorized">
    <h2>My Custom Not Authorized Page</h2>
</template>
```

**In `client.coffee`**

```coffeescript
Template.myNotAuthorized.replaces 'notAuthorized'
```

{% hint style="info" %}
For more detailed information about inheriting and overwriting templates and helpers, see the [official documentation](https://github.com/longshotlabs/meteor-template-extension) for meteor-template-extension.
{% endhint %}

{% hint style="info" %}
Rocket.Chat's theming feature is not fully developed, and developers are highly encouraged to help improve it by contributing to the [related issue](https://github.com/RocketChat/Rocket.Chat/issues/277). If you're working on themes, you're welcome to share your progress in the[#skins-and-theming](https://open.rocket.chat/channel/skins-and-theming) channel on the open server.
{% endhint %}
