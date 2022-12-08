---
description: Updates an existing integration.
---

# Update an Integration

To update an integration, the callee needs to have the permissions `manage-incoming-integrations` AND `manage-own-incoming-integrations` permissions to be able to update incoming integrations and `manage-outgoing-integrations` AND `manage-own-outgoing-integrations` to be able to update outgoing integrations.

| URL                           | Requires Auth | HTTP Method |
| ----------------------------- | ------------- | ----------- |
| `/api/v1/integrations.update` | `yes`         | `PUT`       |

## Payload

| Argument        | Example                                 | Required               | Description                                                                                                                                                                                          |
| --------------- | --------------------------------------- | ---------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `type`          | `webhook-outgoing`                      | Required               | The type of integration to create, `webhook-outgoing` and `webhook-incoming` are supported.                                                                                                          |
| `name`          | `Guggy`                                 | Required               | The name of the integration, only is show on the Administration area.                                                                                                                                |
| `enabled`       | `true`                                  | Required               | Whether this integration should be enabled or not.                                                                                                                                                   |
| `username`      | `rocket.cat`                            | Required               | The username who to post this the messages as.                                                                                                                                                       |
| `channel`       | `#general`                              | Required               | The channel, group, or `@username`. Can also be `all_public_channels`, `all_private_groups`, or `all_direct_messages`. Comma separated for more than one.                                            |
| `scriptEnabled` | `false`                                 | Required               | Whether the script should be enabled.                                                                                                                                                                |
| `urls`          | `['http://text2gif.guggy.com/guggify']` | Optional               | The urls to call whenever this integration is triggered.                                                                                                                                             |
| `event`         | `sendMessage`                           | Optional               | This field is required only for outgoing integration. The type of event, can be any of these: `sendMessage`, `fileUploaded`, `roomArchived`, `roomCreated`, `roomJoined`, `roomLeft`, `userCreated`. |
| `triggerWords`  | `!guggy`                                | Optional Default: `''` | Specific words, separated by commas, which should trigger this integration.                                                                                                                          |
| `alias`         | `Guggy`                                 | Optional Default: `''` | The alias which should be applied to messages when this integration is processed.                                                                                                                    |
| `avatar`        | `http://res.guggy.com/logo_128.png`     | Optional Default: `''` | The logo to apply to the messages that this integration sends.                                                                                                                                       |
| `emoji`         | `:ghost:`                               | Optional Default: `''` | The emoji which should be displayed as the avatar for messages from this integration.                                                                                                                |
| `token`         | `8DFS89DMKLWEN`                         | Optional Default: `''` | If your integration requires a special token from the server (api key), use this.                                                                                                                    |
| `script`        | [Integrations](broken-reference/)       | Optional               | Script triggered when this integration is triggered.                                                                                                                                                 |
| `targetChannel` | `targeted channel`                      | Optional               | The channel where messages will be sent to.                                                                                                                                                          |
| `integrationId` | `ncjK_idsnms`                           | Optional               | The integration ID                                                                                                                                                                                   |
| `target_url`    | `open.rocket.chat`                      | Optional               | The target url to set.                                                                                                                                                                               |

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

{% hint style="info" %}
To update any webhook through API call, the `integrationId` parameter must be included in the request.
{% endhint %}

{% tabs %}
{% tab title="Curl" %}
```
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
{% endtab %}

{% tab title="Node.js" %}
```
var request = require('request');
var options = {
  'method': 'PUT',
  'url': 'http://localhost:3000/api/v1/integrations.update',
  'headers': {
    'X-User-Id': 'd26x6zSkaPSe5gCyy',
    'X-Auth-Token': 'Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({"type":"webhook-incoming","name":"Test","enabled":false,"username":"rocket.cat","scriptEnabled":false,"channel":"#test","integrationId":"x3tPXa9XXRqW6Xp2M"})

};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});
```
{% endtab %}

{% tab title="Python" %}
```
import requests

url = "http://localhost:3000/api/v1/integrations.update"

payload="{\n    \"type\": \"webhook-incoming\",\n    \"name\": \"Test\",\n    \"enabled\": false,\n    \"username\": \"rocket.cat\",\n    \"scriptEnabled\": false,\n    \"channel\": \"#test\",\n    \"integrationId\": \"x3tPXa9XXRqW6Xp2M\"\n}"
headers = {
  'X-User-Id': 'd26x6zSkaPSe5gCyy',
  'X-Auth-Token': 'Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92',
  'Content-Type': 'application/json'
}

response = requests.request("PUT", url, headers=headers, data=payload)

print(response.text)
```
{% endtab %}

{% tab title="PHP" %}
```
<?php
require_once 'HTTP/Request2.php';
$request = new HTTP_Request2();
$request->setUrl('http://localhost:3000/api/v1/integrations.update');
$request->setMethod(HTTP_Request2::METHOD_PUT);
$request->setConfig(array(
  'follow_redirects' => TRUE
));
$request->setHeader(array(
  'X-User-Id' => 'd26x6zSkaPSe5gCyy',
  'X-Auth-Token' => 'Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92',
  'Content-Type' => 'application/json'
));
$request->setBody('{\n    "type": "webhook-incoming",\n    "name": "Test",\n    "enabled": false,\n    "username": "rocket.cat",\n    "scriptEnabled": false,\n    "channel": "#test",\n    "integrationId": "x3tPXa9XXRqW6Xp2M"\n}');
try {
  $response = $request->send();
  if ($response->getStatus() == 200) {
    echo $response->getBody();
  }
  else {
    echo 'Unexpected HTTP status: ' . $response->getStatus() . ' ' .
    $response->getReasonPhrase();
  }
}
catch(HTTP_Request2_Exception $e) {
  echo 'Error: ' . $e->getMessage();
}
```
{% endtab %}

{% tab title="Java" %}
```
Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.put("http://localhost:3000/api/v1/integrations.update")
  .header("X-User-Id", "d26x6zSkaPSe5gCyy")
  .header("X-Auth-Token", "Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92")
  .header("Content-Type", "application/json")
  .body("{\n    \"type\": \"webhook-incoming\",\n    \"name\": \"Test\",\n    \"enabled\": false,\n    \"username\": \"rocket.cat\",\n    \"scriptEnabled\": false,\n    \"channel\": \"#test\",\n    \"integrationId\": \"x3tPXa9XXRqW6Xp2M\"\n}")
  .asString();
```
{% endtab %}
{% endtabs %}

## Example Result

### Success

```javascript
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
