# Update an Integration

To update an integration, the callee needs to have the permissions `manage-incoming-integrations` AND `manage-own-incoming-integrations` permissions to be able to update incoming integrations and `manage-outgoing-integrations` AND `manage-own-outgoing-integrations` to be able to update outgoing integrations.

<table><thead><tr><th width="163">HTTP Method</th><th width="324">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>PUT</code></td><td><code>/api/v1/integrations.update</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="212.33333333333331">Key</th><th width="239">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>type</code><mark style="color:red;"><code>*</code></mark></td><td><code>webhook-outgoing</code></td><td>The type of integration to update, <code>webhook-outgoing</code> and <code>webhook-incoming</code> are supported.</td></tr><tr><td><code>name</code><mark style="color:red;"><code>*</code></mark></td><td><code>Guggy</code></td><td>The name of the integration only is shown in the Administration area.</td></tr><tr><td><code>enabled</code><mark style="color:red;"><code>*</code></mark></td><td><code>true</code></td><td>Whether this integration should be enabled or not.</td></tr><tr><td><code>username</code><mark style="color:red;"><code>*</code></mark></td><td><code>rocket.cat</code></td><td>The username who to post this the messages as.</td></tr><tr><td><code>channel</code><mark style="color:red;"><code>*</code></mark></td><td><code>#general</code></td><td>The channel, group, or <code>@username</code>. Can also be <code>all_public_channels</code>, <code>all_private_groups</code>, or <code>all_direct_messages</code>. Comma separated for more than one.</td></tr><tr><td><code>scriptEnabled</code><mark style="color:red;"><code>*</code></mark></td><td><code>false</code></td><td>Whether the script should be enabled.</td></tr><tr><td><code>integrationId</code><mark style="color:red;"><code>*</code></mark></td><td><code>ncjK_idsnms</code></td><td>The integration ID that you want to update.</td></tr><tr><td><code>urls</code></td><td><code>['http://text2gif.guggy.com/guggify']</code></td><td>The urls to call whenever this integration is triggered.</td></tr><tr><td><code>event</code></td><td><code>sendMessage</code></td><td><p>This field is required only for outgoing integration. </p><p>The type of event can be any of these: <code>sendMessage</code>, <code>fileUploaded</code>, <code>roomArchived</code>, <code>roomCreated</code>, <code>roomJoined</code>, <code>roomLeft</code>, <code>userCreated</code>.</p></td></tr><tr><td><code>triggerWords</code></td><td><code>!guggy</code></td><td>Specific words, separated by commas, which should trigger this integration.</td></tr><tr><td><code>alias</code></td><td><code>Guggy</code></td><td>The alias which should be applied to messages when this integration is processed.</td></tr><tr><td><code>avatar</code></td><td><code>http://res.guggy.com/logo_128.png</code></td><td>The logo to apply to the messages that this integration sends.</td></tr><tr><td><code>emoji</code></td><td><code>:ghost:</code></td><td>The emoji which should be displayed as the avatar for messages from this integration.</td></tr><tr><td><code>token</code></td><td><code>8DFS89DMKLWEN</code></td><td>If your integration requires a special token from the server (api key), use this.</td></tr><tr><td><code>script</code></td><td>Integrations</td><td>Script triggered when this integration is triggered.</td></tr><tr><td><code>targetChannel</code></td><td><code>targeted channel</code></td><td>The channel where messages will be sent to.</td></tr><tr><td><code>target_url</code></td><td><code>open.rocket.chat</code></td><td>The target url to set.</td></tr></tbody></table>

### Example Payload

```
{
    "type": "webhook-incoming",
    "name": "Test",
    "enabled": false,
    "username": "rocket.cat",
    "scriptEnabled": false,
    "channel": "#test",
    "integrationId": "x3tPXa9XXRqW6Xp2M"
}
```

## Example Call

```powershell
curl -L -X PUT 'http://localhost:3000/api/v1/integrations.update' \
-H 'X-User-Id: d26x6zSkaPSe5gCyy' \
-H 'X-Auth-Token: Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92' \
-H 'Content-Type: application/json' \
--data-raw '{
    "type": "webhook-incoming",
    "name": "Test",
    "enabled": false,
    "username": "rocket.cat",
    "scriptEnabled": false,
    "channel": "#test",
    "integrationId": "x3tPXa9XXRqW6Xp2M"
}'
```

## Example Response

### Success

```json
{
    "integration": {
        "_id": "x3tPXa9XXRqW6Xp2M",
        "enabled": false,
        "channel": [
            "#test"
        ],
        "username": "rodriq",
        "name": "Test",
        "alias": "Jim",
        "avatarUrl": "",
        "emoji": ":ghost:",
        "scriptEnabled": false,
        "script": "console.log(\"MANNNNN ---------------------------------------------------------\")",
        "type": "webhook-incoming",
        "token": "XYsrkngRr5PBkWhCqJWk5ZfKzQoxSv4QhxkK5trSgJENwbRL",
        "userId": "d26x6zSkaPSe5gCyy",
        "_createdAt": "2021-10-22T14:48:46.025Z",
        "_createdBy": {
            "_id": "d26x6zSkaPSe5gCyy",
            "username": "rodriq"
        },
        "_updatedAt": "2021-10-22T16:08:39.843Z",
        "_updatedBy": {
            "_id": "d26x6zSkaPSe5gCyy",
            "username": "rodriq"
        }
    },
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **Missing Key**: Triggers when the endpoint is called without any required endpoint.
* **No integration Found**: You get this error when the integration you're trying to update is not found.

{% tabs %}
{% tab title=" Authorization" %}
```javascript
{
    "success": false,
    "error": "unauthorized"
}
```
{% endtab %}

{% tab title="Missing Key" %}
```
{
    "success": false,
    "error": "Match error: Missing key '<key name>'"
}
```
{% endtab %}

{% tab title="No Integration Found" %}
```
{
    "success": false,
    "error": "No integration found."
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 3.4.0   | Added       |
