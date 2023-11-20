# Extend App Capabilities

After learning how to create and deploy a basic app, you can now extend the app to add more features such as slash commands, HTTP requests, handling events, and UI interactions supported by the Apps-Engine to expand the functionality of your app to meet business requirements.

The [`IConfigurationExtend`](https://rocketchat.github.io/Rocket.Chat.Apps-engine/interfaces/accessors\_IConfigurationExtend.IConfigurationExtend.html) accessor contains methods to declare your app's configuration. It is created during app initialization. Using this, you can add new features to your app.

Here is a list of accessors that Apps-Engine supports:

<table><thead><tr><th width="230.5">Accessor</th><th>Description</th></tr></thead><tbody><tr><td><code>api</code></td><td>Declare API endpoints.</td></tr><tr><td><code>http</code></td><td>Configure how your app handles HTTP requests and responses.</td></tr><tr><td><code>scheduler</code></td><td>Designate tasks that can be scheduled.</td></tr><tr><td><code>settings</code></td><td>Declare the configurations of your app.</td></tr><tr><td><code>slashCommands</code></td><td>Declare the commands that your app offers.</td></tr><tr><td><code>ui</code></td><td>Register various host UI elements.</td></tr><tr><td><code>videoConfProviders</code></td><td>Declare the video conferencing providers that your app offers.</td></tr></tbody></table>

In the following sections, we will learn how to implement these accessors in our apps.
