# Create Integration

Creates an integration, if the callee has the permissions.&#x20;

Permissions required to create incoming integrations:

* `manage-incoming-integrations`
* `manage-own-incoming-integrations`

Permissions required to create incoming integrations:

* `manage-outgoing-integrations`
* `manage-own-outgoing-integrations`

<table><thead><tr><th width="163">HTTP Method</th><th width="324">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/integrations.create</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Incoming Webhook

### Body Parameters

<table><thead><tr><th width="222.33333333333331">Key</th><th width="217">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>type</code><mark style="color:red;"><code>*</code></mark></td><td><code>webhook-incoming</code></td><td>The type of integration to create.</td></tr><tr><td><code>username</code><mark style="color:red;"><code>*</code></mark></td><td><code>rocket.cat</code></td><td>The username who to post this the messages as.</td></tr><tr><td><code>channel</code><mark style="color:red;"><code>*</code></mark></td><td><code>#general</code></td><td>The channel, group, or <code>@username</code>. Can also be <code>all_public_channels</code>, <code>all_private_groups</code>, or <code>all_direct_messages</code>. Comma separated for more than one.</td></tr><tr><td><code>scriptEnabled</code><mark style="color:red;"><code>*</code></mark></td><td><code>sendMessage</code></td><td>Whether the script should be enabled.</td></tr><tr><td><code>script</code></td><td><code>Integration</code></td><td>Script triggered when this integration is triggered.</td></tr><tr><td><code>name</code><mark style="color:red;"><code>*</code></mark></td><td><code>rocket.cat</code></td><td>The username who to post this the messages as.</td></tr><tr><td><code>enabled</code><mark style="color:red;"><code>*</code></mark></td><td><code>true</code></td><td>Whether this integration should be enabled or not.</td></tr><tr><td><code>alias</code></td><td><code>Guggy</code></td><td>The alias which should be applied to messages when this integration is processed.</td></tr><tr><td><code>avatar</code></td><td><code>http://res.guggy.com/logo_128.png</code></td><td>The logo to apply to the messages that this integration sends.</td></tr><tr><td><code>emoji</code></td><td><code>:ghost:</code></td><td>The emoji which should be displayed as the avatar for messages from this integration.</td></tr></tbody></table>

### Example Call

```powershell
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/integrations.create \
     -d '{ 
          "type": "webhook-incoming", 
          "username": "rocket.cat", 
          "channel": "#general", 
          "scriptEnabled": false,
          "name": "testHook",
          "enabled": true }'
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

### Body Parameters

<table><thead><tr><th width="214.33333333333331">Key</th><th width="213">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>type</code><mark style="color:red;"><code>*</code></mark></td><td><code>webhook-outgoing</code></td><td>The type of integration to create, <code>webhook-outgoing</code> and <code>webhook-incoming</code> are supported.</td></tr><tr><td><code>name</code><mark style="color:red;"><code>*</code></mark></td><td><code>Guggy</code></td><td>The name of the integration, only is show on the Administration area.</td></tr><tr><td><code>enabled</code><mark style="color:red;"><code>*</code></mark></td><td><code>true</code></td><td>Whether this integration should be enabled or not.</td></tr><tr><td><code>event</code><mark style="color:red;"><code>*</code></mark></td><td><code>sendMessage</code></td><td>This field is required only for outgoing integration. The type of event, can be any of these: <code>sendMessage</code>, <code>fileUploaded</code>, <code>roomArchived</code>, <code>roomCreated</code>, <code>roomJoined</code>, <code>roomLeft</code>, <code>userCreated</code>.</td></tr><tr><td><code>username</code><mark style="color:red;"><code>*</code></mark></td><td><code>rocket.cat</code></td><td>The username who to post this the messages as.</td></tr><tr><td><code>urls</code><mark style="color:red;"><code>*</code></mark></td><td><code>['http://text2gif.guggy.com/guggify']</code></td><td>The urls to call whenever this integration is triggered.</td></tr><tr><td><code>scriptEnabled</code><mark style="color:red;"><code>*</code></mark></td><td><code>false</code></td><td>Whether the script should be enabled.</td></tr><tr><td><code>channel</code><mark style="color:red;"><code>*</code></mark></td><td><code>#general</code></td><td>The channel, group, or <code>@username</code>. Can also be <code>all_public_channels</code>, <code>all_private_groups</code>, or <code>all_direct_messages</code>. Comma separated for more than one.</td></tr><tr><td><code>triggerWords</code></td><td><code>!guggy</code></td><td>Specific words, separated by commas, which should trigger this integration.</td></tr><tr><td><code>alias</code></td><td><code>Guggy</code></td><td>The alias which should be applied to messages when this integration is processed.</td></tr><tr><td><code>avatar</code></td><td><code>http://res.guggy.com/logo_128.png</code></td><td>The logo to apply to the messages that this integration sends.</td></tr><tr><td><code>emoji</code></td><td><code>:ghost:</code></td><td>The emoji which should be displayed as the avatar for messages from this integration.</td></tr><tr><td><code>token</code></td><td><code>8DFS89DMKLWEN</code></td><td>If your integration requires a special token from the server (api key), use this.</td></tr><tr><td><code>script</code></td><td>Integrations</td><td>Script triggered when this integration is triggered.</td></tr></tbody></table>

### Example Call

```powershell
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/integrations.create \
     -d '{ 
          "type": "webhook-outgoing", 
          "name": "Testing via REST API", 
          "event": "sendMessage", 
          "enabled": false, 
          "channel": "#general", 
          "username": "rocket.cat", 
          "urls": ["http://text2gif.guggy.com/guggify"], 
          "scriptEnabled": false }'
```

### Example Response

```json
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
