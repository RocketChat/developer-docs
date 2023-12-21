# App Permission System

Each feature available in the Apps-Engine is mapped to a permission. Adding the permission in the app's manifest (`app.json` file) will unlock said feature to be used by the app. For example, if you add the `send messages` permission to your app's manifest, your app can send messages in the Rocket.Chat server. If your app tries to send a message without having the `send messages` permission listed in the manifest, Apps-Engine will block the feature, and the app will not be able to perform the desired action.

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

## List of permissions

Here is a list of the permissions that you need to add to your app:

<table><thead><tr><th width="356">Permission</th><th>Description</th></tr></thead><tbody><tr><td><code>user.read</code></td><td>Access user information</td></tr><tr><td><code>user.write</code></td><td>Modify user information</td></tr><tr><td><code>upload.read</code></td><td>Access files uploaded to the server</td></tr><tr><td><code>upload.write</code></td><td>Upload files to the server</td></tr><tr><td><code>server-setting.read</code></td><td>Access settings in the server</td></tr><tr><td><code>server-setting.write</code></td><td>Modify settings in the server</td></tr><tr><td><code>room.read</code></td><td>Access room information</td></tr><tr><td><code>room.write</code></td><td>Create and modify rooms</td></tr><tr><td><code>role.read</code></td><td>Access user roles</td></tr><tr><td><code>role.write</code></td><td>Modify user roles</td></tr><tr><td><code>message.read</code></td><td>Access messages</td></tr><tr><td><code>message.write</code></td><td>Send and modify messages</td></tr><tr><td><code>moderation.read</code></td><td>Access to read moderation dashboard information</td></tr><tr><td><code>moderation.write</code></td><td>Modify moderation dashboard information</td></tr><tr><td><code>threads.read</code></td><td>Access threads. Effectively allows the app to read all messages in a thread</td></tr><tr><td><code>livechat-status.read</code></td><td>Access Livechat status information</td></tr><tr><td><code>livechat-custom-fields.write</code></td><td>Modify Livechat custom field configuration</td></tr><tr><td><code>livechat-visitor.read</code></td><td>Access Livechat visitor information</td></tr><tr><td><code>livechat-visitor.write</code></td><td>Modify Livechat visitor information</td></tr><tr><td><code>livechat-message.read</code></td><td>Access Livechat message information</td></tr><tr><td><code>livechat-message.write</code></td><td>Modify Livechat message information</td></tr><tr><td><code>livechat-message.multiple</code></td><td>Access to read multiple messages at once</td></tr><tr><td><code>livechat-room.read</code></td><td>Access Livechat room information</td></tr><tr><td><code>livechat-room.write</code></td><td>Modify Livechat room information</td></tr><tr><td><code>livechat-department.read</code></td><td>Access Livechat department information</td></tr><tr><td><code>livechat-department.write</code></td><td>Modify Livechat department information</td></tr><tr><td><code>livechat-department.multiple</code></td><td>Access to read multiple departments at once</td></tr><tr><td><code>env.read</code></td><td>Access minimal information about the server environment</td></tr><tr><td><code>cloud.workspace-token</code></td><td>Access to request the workspace access token to interact with Rocket.Chat's Cloud Systems</td></tr><tr><td><code>ui.interact</code></td><td>Interact with the UI (UIKit)</td></tr><tr><td><code>ui.registerButtons</code></td><td>Use UIKit buttons</td></tr><tr><td><code>scheduler</code></td><td>Register and maintain scheduled jobs</td></tr><tr><td><code>networking</code></td><td>Register and maintain scheduled jobs</td></tr><tr><td><code>persistence</code></td><td>Store internal data in the database</td></tr><tr><td><code>slashcommand</code></td><td>Register new slash commands</td></tr><tr><td><code>video-conference.read</code></td><td>Access to read video conference information</td></tr><tr><td><code>video-conference.write</code></td><td>Modify video conference information</td></tr><tr><td><code>video-conference-provider</code></td><td>Act as a video conference provider in Rocket.Chat</td></tr><tr><td><code>api</code></td><td>Register new HTTP endpoints</td></tr><tr><td><code>oauth-app.read</code></td><td>Access OAuth information</td></tr><tr><td><code>oauth-app.write</code></td><td>Modify OAuth information</td></tr></tbody></table>

{% hint style="info" %}
For an example of how these permissions are used in apps, refer to the [Action Buttons](extend-app-capabilities/apps-engine-user-interface/action-buttons.md) topic.
{% endhint %}

### Default permissions

Out of the permissions listed above, the following permissions are present by default to ensure backward compatibility for apps that were developed before the permission system was introduced.

```typescript
    user.read,
    user.write,
    
    upload.read,
    upload.write,
    
    ui.interaction,
    
    setting.read,
    setting.write,
    
    room.read,
    room.write,
    
    message.read,
    message.write,
    
    livechat-department.read,
    livechat-department.write,
    
    livechat-room.read,
    livechat-room.write,
    
    livechat-message.read,
    livechat-message.write,
    
    livechat-visitor.read,
    livechat-visitor.write,
    
    livechat-status.read,
    
    livechat-custom-fields.write,
    
    scheduler.default,
    networking.default,
    persistence.default,
    env.read,
    command.default,
    
    videoConference.provider,
    videoConference.read,
    videoConference.write,
    
    apis.default
```

Once an app is on the Rocket.Chat workspace, it goes through several lifecycle phases unique to Rocket.Chat. The phases depend on the capabilities that your app has. To learn about the app lifecycle, head over to the next page.
