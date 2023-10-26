# Extending App Capabilities

The `IConfigurationExtend` accessor contains methods to declare your app's configuration. It is created during the app initialization. Using this, you can add new features to your app.

Here is a list of accessors that Apps-Engine supports:

<table><thead><tr><th width="230.5">Accessor</th><th>Description</th></tr></thead><tbody><tr><td><code>api</code></td><td>Declare API endpoints.</td></tr><tr><td><code>http</code></td><td>Configure how your app handles HTTP requests and responses.</td></tr><tr><td><code>scheduler</code></td><td>Designate tasks that can be scheduled.</td></tr><tr><td><code>settings</code></td><td>Declare the configurations of your app.</td></tr><tr><td><code>slashCommands</code></td><td>Declare the commands that your app offers.</td></tr><tr><td><code>ui</code></td><td>Register various host UI elements.</td></tr><tr><td><code>videoConfProviders</code></td><td>Declare the video conferencing providers that your app offers.</td></tr></tbody></table>
