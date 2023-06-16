# Permission System

## How it works

Each feature available in the Apps-Engine is mapped to a permission. Adding the permission in the app's manifest (`app.json` file) will unlock said feature to be used by the app. For example, if you add "send messages" as a permission in your app's manifest, your app will be able to send messages in the Rocket.Chat server. If your app tries to send a message without having the "send messages" permission listed in the manifest, the Apps-Engine will block the feature and the app will not be able to perform the desired action.

When installing an app, be it by the Marketplace or installing it manually via zip file, a window asks the user to review the permissions the app requires to work properly. The user installing the app can either accept and install the app or deny the permissions and not install it.

## How to use it

In your app's manifest file (`app.json`), add the field `permissions`. It receives a list containing all the permissions you are asking for. Example:

```javascript
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

As of right now, the Apps-Engine does not enforce the use of the permissions to make your apps work, meaning your current apps (including the ones published at the Marketplace) will still work as expected. All the apps that do not have the permissions listed in their manifest will still have access to all the features they need through the `default permissions`. They are applied to your app automatically when no `permissions` property is found in the app's manifest.

Until no sunsetting period for the "permissionless engine" is defined, setting permissions in your app's manifest will be optional.

## Permissions

Here is a list of permissions available:

| Permission Name                | Description                                             |
| ------------------------------ | ------------------------------------------------------- |
| `user.read`                    | Access user information                                 |
| `user.write`                   | Modify user information                                 |
| `upload.read`                  | Access files uploaded to the server                     |
| `upload.write`                 | Upload files to the server                              |
| `server-setting.read`          | Access settings in the server                           |
| `server-setting.write`         | Modify settings in the server                           |
| `room.read`                    | Access room information                                 |
| `room.write`                   | Create and modify rooms                                 |
| `message.read`                 | Access messages                                         |
| `message.write`                | Send and modify messages                                |
| `livechat-status.read`         | Access Livechat status information                      |
| `livechat-custom-fields.write` | Modify Livechat custom field configuration              |
| `livechat-visitor.read`        | Access Livechat visitor information                     |
| `livechat-visitor.write`       | Modify Livechat visitor information                     |
| `livechat-message.read`        | Access Livechat message information                     |
| `livechat-message.write`       | Modify Livechat message information                     |
| `livechat-room.read`           | Access Livechat room information                        |
| `livechat-room.write`          | Modify Livechat room information                        |
| `livechat-department.read`     | Access Livechat department information                  |
| `livechat-department.write`    | Modify Livechat department information                  |
| `slashcommand`                 | Register new slash commands                             |
| `apis`                         | Register new HTTP endpoints                             |
| `env.read`                     | Access minimal information about the server environment |
| `networking`                   | Access to the server network                            |
| `persistence`                  | Store internal data in the database                     |
| `scheduler`                    | Register and maintain scheduled jobs                    |
| `ui.interact`                  | Interact with the UI (UIKit)                            |
