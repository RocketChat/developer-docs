# Create Integration

Creates an integration, if the callee has the permissions. Requires `manage-incoming-integrations` AND `manage-own-incoming-integrations` permissions to be able to create incoming integrations and `manage-outgoing-integrations` AND `manage-own-outgoing-integrations` to be able to create outgoing integrations.

| URL                           | Requires Auth | HTTP Method |
| ----------------------------- | ------------- | ----------- |
| `/api/v1/integrations.create` | `yes`         | `POST`      |

## Incoming Webhook

### Payload

<table><thead><tr><th>Argument</th><th>Example</th><th width="150">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>type</code></td><td><code>webhook-incoming</code></td><td>Required</td><td>The type of integration to create.</td></tr><tr><td><code>username</code></td><td><code>rocket.cat</code></td><td>Required</td><td>The username who to post this the messages as.</td></tr><tr><td><code>channel</code></td><td><code>#general</code></td><td>Required</td><td>The channel, group, or <code>@username</code>. Can also be <code>all_public_channels</code>, <code>all_private_groups</code>, or <code>all_direct_messages</code>. Comma separated for more than one.</td></tr><tr><td><code>scriptEnabled</code></td><td><code>sendMessage</code></td><td>Required</td><td>Whether the script should be enabled.</td></tr><tr><td><code>script</code></td><td><code>Integration</code></td><td>Optional</td><td>Script triggered when this integration is triggered.</td></tr><tr><td><code>name</code></td><td><code>rocket.cat</code></td><td>Required</td><td>The username who to post this the messages as.</td></tr><tr><td><code>enabled</code></td><td><code>true</code></td><td>Required</td><td>Whether this integration should be enabled or not.</td></tr><tr><td><code>alias</code></td><td><code>Guggy</code></td><td>Optional Default: <code>''</code></td><td>The alias which should be applied to messages when this integration is processed.</td></tr><tr><td><code>avatar</code></td><td><code>http://res.guggy.com/logo_128.png</code></td><td>Optional Default: <code>''</code></td><td>The logo to apply to the messages that this integration sends.</td></tr><tr><td><code>emoji</code></td><td><code>:ghost:</code></td><td>Optional Default: <code>''</code></td><td>The emoji which should be displayed as the avatar for messages from this integration.</td></tr></tbody></table>

### Example Call

```json
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/integrations.create \
     -d '{ "type": "webhook-incoming", "username": "rocket.cat", "channel": "#general", "scriptEnabled": false }'
```

### Example Response

```json
{
    "integration": {
        "type": "webhook-incoming",
        "username": "rocket.cat",
        "channel": false,
        "scriptEnabled": "sendMessage",
        "name": "sendMessage",
        "enabled": "sendMessage",
        }
```

## Outgoing Webhook

### Payload

| Argument        | Example                                                                   | Required               | Description                                                                                                                                                                                          |
| --------------- | ------------------------------------------------------------------------- | ---------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `type`          | `webhook-outgoing`                                                        | Required               | The type of integration to create, `webhook-outgoing` and `webhook-incoming` are supported.                                                                                                          |
| `name`          | `Guggy`                                                                   | Required               | The name of the integration, only is show on the Administration area.                                                                                                                                |
| `enabled`       | `true`                                                                    | Required               | Whether this integration should be enabled or not.                                                                                                                                                   |
| `event`         | `sendMessage`                                                             | Required               | This field is required only for outgoing integration. The type of event, can be any of these: `sendMessage`, `fileUploaded`, `roomArchived`, `roomCreated`, `roomJoined`, `roomLeft`, `userCreated`. |
| `username`      | `rocket.cat`                                                              | Required               | The username who to post this the messages as.                                                                                                                                                       |
| `urls`          | `['http://text2gif.guggy.com/guggify']`                                   | Required               | The urls to call whenever this integration is triggered.                                                                                                                                             |
| `scriptEnabled` | `false`                                                                   | Required               | Whether the script should be enabled.                                                                                                                                                                |
| `channel`       | `#general`                                                                | Required               | The channel, group, or `@username`. Can also be `all_public_channels`, `all_private_groups`, or `all_direct_messages`. Comma separated for more than one.                                            |
| `triggerWords`  | `!guggy`                                                                  | Optional Default: `''` | Specific words, separated by commas, which should trigger this integration.                                                                                                                          |
| `alias`         | `Guggy`                                                                   | Optional Default: `''` | The alias which should be applied to messages when this integration is processed.                                                                                                                    |
| `avatar`        | `http://res.guggy.com/logo_128.png`                                       | Optional Default: `''` | The logo to apply to the messages that this integration sends.                                                                                                                                       |
| `emoji`         | `:ghost:`                                                                 | Optional Default: `''` | The emoji which should be displayed as the avatar for messages from this integration.                                                                                                                |
| `token`         | `8DFS89DMKLWEN`                                                           | Optional Default: `''` | If your integration requires a special token from the server (api key), use this.                                                                                                                    |
| `script`        | [Integrations](../core-endpoints/integration-endpoints/broken-reference/) | Optional               | Script triggered when this integration is triggered.                                                                                                                                                 |

### Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/integrations.create \
     -d '{ "type": "webhook-outgoing", "name": "Testing via REST API", "event": "sendMessage", "enabled": false, "channel": "#general", "username": "rocket.cat", "urls": ["http://text2gif.guggy.com/guggify"], "scriptEnabled": false }'
```

### Example Result

```javascript
{
    "integration": {
        "type": "webhook-outgoing",
        "name": "Testing via REST API",
        "enabled": false,
        "username": "rocket.cat",
        "event": "sendMessage",
        "urls": [
            "http://text2gif.guggy.com/guggify"
        ],
        "scriptEnabled": false,
        "userId": "rocket.cat",
        "channel": [],
        "_createdAt": "2017-01-06T13:23:46.018Z",
        "_createdBy": {
            "username": "graywolf336",
            "_id": "aobEdbYhXfu5hkeqG"
        },
        "_updatedAt": "2017-01-06T13:23:46.018Z",
        "_id": "3aazpZ2WzoBP8msi9"
    },
    "success": true
}
```

## Change Log

| Version | Description                                        |
| ------- | -------------------------------------------------- |
| 1.1.0   | Separate permissions in `incoming` and `outgoing`. |
| 0.49.0  | Added                                              |
