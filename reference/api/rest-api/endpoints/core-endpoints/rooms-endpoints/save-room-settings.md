# Save Room Settings

This endpoint allows you to save the settings of a room.

| URL                              | Requires Auth | HTTP Method |
| -------------------------------- | ------------- | ----------- |
| `/api/v1/rooms.saveRoomSettings` | `yes`         | `POST`      |

## Payload

| `rid`                   | `JZ8Y2dLfYhsg323Rf`                         | Required | The room id.                                                                                                         |
| ----------------------- | ------------------------------------------- | -------- | -------------------------------------------------------------------------------------------------------------------- |
| `roomName`              | `Test-Save-Room`                            | Optional | The name of the room.                                                                                                |
| `roomDescription`       | `This is a test room.`                      | Optional | The description of the room.                                                                                         |
| roomAvatar              | https://example.com/image                   | Optional | The URL of the room avatar image.                                                                                    |
| featured                | true                                        | Optional | Whether the room is featured or not.                                                                                 |
| roomTopic               | Discussion Topic                            | Optional | The topic of the room.                                                                                               |
| roomAnnouncement        | Important Announcement                      | Optional | The announcement of the room.                                                                                        |
| roomCustomFields        | { "field1": "value1" }                      | Optional | The custom fields of the room.                                                                                       |
| roomType                | "c"                                         | Optional | The type of the room.                                                                                                |
| readOnly                | true                                        | Optional | Whether the room is read-only or not.                                                                                |
| reactWhenReadOnly       | true                                        | Optional | Whether users can react when the room is read-only.                                                                  |
| systemMessages          | \["changed-room-name"]                      | Optional | The system messages that the room supports.                                                                          |
| default                 | true                                        | Optional | Whether the room is the default room or not.                                                                         |
| joinCode                | "123456"                                    | Optional | The join code of the room.                                                                                           |
| streamingOptions        | { "type": "live" }                          | Optional | The streaming options of the room.                                                                                   |
| retentionEnabled        | true                                        | Optional | Whether retention is enabled for the room or not.                                                                    |
| retentionMaxAge         | 30                                          | Optional | The maximum age (in days) of messages to be retained in the room.                                                    |
| retentionExcludePinned  | true                                        | Optional | Whether to exclude pinned messages from retention or not.                                                            |
| retentionFilesOnly      | true                                        | Optional | Whether to retain only files in the room or not.                                                                     |
| retentionIgnoreThreads  | true                                        | Optional | Whether to ignore threads when retaining messages or not.                                                            |
| retentionOverrideGlobal | true                                        | Optional | Whether to override the global retention settings for the room or not.                                               |
| encrypted               | true                                        | Optional | Whether the room is encrypted or not.                                                                                |
| favorite                | { "favorite": true, "defaultValue": false } | Optional | The favorite settings of the room. Whether the room is marked as favorite and whether it is set as the default room. |

### Example Payload

```
{
    "rid": "JZ8Y2dLfYhsg323Rf",
    "roomName": "Test-Save-Room",
    "roomDescription": "This is a test for save-room settings."
}
```

## Example Call

{% tabs %}
{% tab title="Curl" %}
```
curl -L -X POST 'http://localhost:3000/api/v1/rooms.saveRoomSettings' \
-H 'X-User-Id: d26x6zSkaPSe5gCyy' \
-H 'X-Auth-Token: Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92' \
-H 'Content-Type: application/json' \
--data-raw '{
    "rid": "JZ8Y2dLfYhsg323Rf",
    "roomName": "Test-Save-Room",
    "roomDescription": "This is a test room."
}'
```
{% endtab %}

{% tab title="Node.js" %}
```
var request = require('request');
var options = {
  'method': 'POST',
  'url': 'http://localhost:3000/api/v1/rooms.saveRoomSettings',
  'headers': {
    'X-User-Id': 'd26x6zSkaPSe5gCyy',
    'X-Auth-Token': 'Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({"rid":"JZ8Y2dLfYhsg323Rf"})

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

url = "http://localhost:3000/api/v1/rooms.saveRoomSettings"

payload="{\n    \"rid\": \"JZ8Y2dLfYhsg323Rf\"\n}"
headers = {
  'X-User-Id': 'd26x6zSkaPSe5gCyy',
  'X-Auth-Token': 'Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92',
  'Content-Type': 'application/json'
}

response = requests.request("POST", url, headers=headers, data=payload)

print(response.text)
```
{% endtab %}

{% tab title="PHP" %}
```
<?php
require_once 'HTTP/Request2.php';
$request = new HTTP_Request2();
$request->setUrl('http://localhost:3000/api/v1/rooms.saveRoomSettings');
$request->setMethod(HTTP_Request2::METHOD_POST);
$request->setConfig(array(
  'follow_redirects' => TRUE
));
$request->setHeader(array(
  'X-User-Id' => 'd26x6zSkaPSe5gCyy',
  'X-Auth-Token' => 'Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92',
  'Content-Type' => 'application/json'
));
$request->setBody('{\n    "rid": "JZ8Y2dLfYhsg323Rf"\n}');
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
HttpResponse<String> response = Unirest.post("http://localhost:3000/api/v1/rooms.saveRoomSettings")
  .header("X-User-Id", "d26x6zSkaPSe5gCyy")
  .header("X-Auth-Token", "Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92")
  .header("Content-Type", "application/json")
  .body("{\n    \"rid\": \"JZ8Y2dLfYhsg323Rf\"\n}")
  .asString();
```
{% endtab %}
{% endtabs %}

## Example Result

### Success

```javascript
{
    "rid": "JZ8Y2dLfYhsg323Rf",
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **Invalid Room**: Occurs when the given `rid` is invalid.

{% tabs %}
{% tab title=" Authorization" %}
```javascript
{
    "success": false,
    "error": "unauthorized"
}
```
{% endtab %}

{% tab title="Invalid Room ID" %}
```
{
    "success": false,
    "error": "The required \"roomId\" or \"roomName\" param provided does not match any group [error-room-not-found]",
    "errorType": "error-room-not-found"
}
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 3.13.0  | Added       |
