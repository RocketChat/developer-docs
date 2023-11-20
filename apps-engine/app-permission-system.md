# App Permission System

Each feature available in the Apps-Engine is mapped to a permission. Adding the permission in the app's manifest (`app.json` file) will unlock said feature to be used by the app. For example, if you add the `send messages` permission to your app's manifest, your app can send messages in the Rocket.Chat server. If your app tries to send a message without having the `send messages` permission listed in the manifest, Apps-Engine will block the feature and the app will not be able to perform the desired action.

When installing an app, be it via the Marketplace or installing it manually via zip file, a window asks the user to review the permissions that the app requires to work properly. The user installing the app can either accept and install the app or deny the permissions and not install it.

## Add permissions to your app

In your app's manifest file (`app.json`), add the field `permissions`. It receives a list containing all the permissions that you are asking for. For example:

```json
{
...
"permissions": [
    {
        "name": "user.read"
    },
    {
        "name": "user.write"
    },
    {
        "name": "upload.read"
    },
  ],
...
}
```

### Notice about rule enforcement

Currently, the Apps-Engine does not enforce the use of the permissions to make your apps work, meaning your current apps (including those published on the Marketplace) will still work as expected. All the apps that do not have the permissions listed in their manifest will still have access to all the features they need through `default permissions`. They are applied to your app automatically when no `permissions` property is found in the app's manifest.

Until the sunsetting period for the "permissionless engine" is not defined, setting permissions in your app's manifest will be optional.

## List of permissions

Here is a list of the available permissions:

<table><thead><tr><th width="356">Permission Name</th><th>Description</th></tr></thead><tbody><tr><td><code>user.read</code></td><td>Access user information</td></tr><tr><td><code>user.write</code></td><td>Modify user information</td></tr><tr><td><code>upload.read</code></td><td>Access files uploaded to the server</td></tr><tr><td><code>upload.write</code></td><td>Upload files to the server</td></tr><tr><td><code>server-setting.read</code></td><td>Access settings in the server</td></tr><tr><td><code>server-setting.write</code></td><td>Modify settings in the server</td></tr><tr><td><code>room.read</code></td><td>Access room information</td></tr><tr><td><code>room.write</code></td><td>Create and modify rooms</td></tr><tr><td><code>message.read</code></td><td>Access messages</td></tr><tr><td><code>message.write</code></td><td>Send and modify messages</td></tr><tr><td><code>livechat-status.read</code></td><td>Access Livechat status information</td></tr><tr><td><code>livechat-custom-fields.write</code></td><td>Modify Livechat custom field configuration</td></tr><tr><td><code>livechat-visitor.read</code></td><td>Access Livechat visitor information</td></tr><tr><td><code>livechat-visitor.write</code></td><td>Modify Livechat visitor information</td></tr><tr><td><code>livechat-message.read</code></td><td>Access Livechat message information</td></tr><tr><td><code>livechat-message.write</code></td><td>Modify Livechat message information</td></tr><tr><td><code>livechat-room.read</code></td><td>Access Livechat room information</td></tr><tr><td><code>livechat-room.write</code></td><td>Modify Livechat room information</td></tr><tr><td><code>livechat-department.read</code></td><td>Access Livechat department information</td></tr><tr><td><code>livechat-department.write</code></td><td>Modify Livechat department information</td></tr><tr><td><code>slashcommand</code></td><td>Register new slash commands</td></tr><tr><td><code>apis</code></td><td>Register new HTTP endpoints</td></tr><tr><td><code>env.read</code></td><td>Access minimal information about the server environment</td></tr><tr><td><code>networking</code></td><td>Access to the server network</td></tr><tr><td><code>persistence</code></td><td>Store internal data in the database</td></tr><tr><td><code>scheduler</code></td><td>Register and maintain scheduled jobs</td></tr><tr><td><code>ui.interact</code></td><td>Interact with the UI (UIKit)</td></tr></tbody></table>

Once an app is on the Rocket.Chat workspace, it goes through several lifecycle phases unique to Rocket.Chat. The phases depend on the capabilities that your app has. To learn about the app lifecycle, head over to the next page.
