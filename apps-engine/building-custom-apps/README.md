# Extending App Capabilities

`IConfigurationExtend` is the accessor that offers methods for declaring your application's configuration. It is provided during application initialization. This is how the app can be expanded or new features added. Register some of your app's capabilities using this method.

<table><thead><tr><th width="221.5">Property</th><th>Purpose</th></tr></thead><tbody><tr><td>api</td><td>Accessor for API endpoint declarations</td></tr><tr><td>http</td><td>Accessor for configuring how your application handles HTTP requests and responses</td></tr><tr><td>scheduler</td><td>Accessor for designating tasks that can be scheduled</td></tr><tr><td>settings</td><td>Accessor for declaring the configurations your app offers</td></tr><tr><td>slashCommands</td><td>Accessor for declaring the commands that your app provides</td></tr><tr><td>ui</td><td>Accessor for registering the various host UI elements</td></tr><tr><td>videoConfProviders</td><td>Accessor for declaring the video conferencing providers your app offers</td></tr></tbody></table>

