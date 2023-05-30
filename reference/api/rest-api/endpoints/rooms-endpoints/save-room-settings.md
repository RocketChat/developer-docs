# Save Room Settings

This endpoint allows you to save the settings of a room.

| URL                              | Requires Auth | HTTP Method |
| -------------------------------- | ------------- | ----------- |
| `/api/v1/rooms.saveRoomSettings` | `yes`         | `POST`      |

## Payload

<table data-header-hidden><thead><tr><th width="180">Argument</th><th width="182">Example</th><th width="139">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>rid</code></td><td><code>JZ8Y2dLfYhsg323Rf</code></td><td>Required</td><td>The room id.</td></tr><tr><td><code>roomName</code></td><td><code>Test-Save-Room</code></td><td>Optional</td><td>The name of the room.</td></tr><tr><td><code>roomDescription</code></td><td><code>This is a test room.</code></td><td>Optional</td><td>The description of the room.</td></tr><tr><td>roomAvatar</td><td>https://example.com/image</td><td>Optional</td><td>The URL of the room avatar image.</td></tr><tr><td>featured</td><td>true</td><td>Optional</td><td>Whether the room is featured or not.</td></tr><tr><td>roomTopic</td><td>Discussion Topic</td><td>Optional</td><td>The topic of the room.</td></tr><tr><td>roomAnnouncement</td><td>Important Announcement</td><td>Optional</td><td>The announcement of the room.</td></tr><tr><td>roomCustomFields</td><td>{ "field1": "value1" }</td><td>Optional</td><td>The custom fields of the room.</td></tr><tr><td>roomType</td><td>"c"</td><td>Optional</td><td>The type of the room.</td></tr><tr><td>readOnly</td><td>true</td><td>Optional</td><td>Whether the room is read-only or not.</td></tr><tr><td>reactWhenReadOnly</td><td>true</td><td>Optional</td><td>Whether users can react when the room is read-only.</td></tr><tr><td>systemMessages</td><td>["changed-room-name"]</td><td>Optional</td><td>The system messages that the room supports.</td></tr><tr><td>default</td><td>true</td><td>Optional</td><td>Whether the room is the default room or not.</td></tr><tr><td>joinCode</td><td>"123456"</td><td>Optional</td><td>The join code of the room.</td></tr><tr><td>streamingOptions</td><td>{ "type": "live" }</td><td>Optional</td><td>The streaming options of the room.</td></tr><tr><td>retentionEnabled</td><td>true</td><td>Optional</td><td>Whether retention is enabled for the room or not.</td></tr><tr><td>retentionMaxAge</td><td>30</td><td>Optional</td><td>The maximum age (in days) of messages to be retained in the room.</td></tr><tr><td>retentionExcludePinned</td><td>true</td><td>Optional</td><td>Whether to exclude pinned messages from retention or not.</td></tr><tr><td>retentionFilesOnly</td><td>true</td><td>Optional</td><td>Whether to retain only files in the room or not.</td></tr><tr><td>retentionIgnoreThreads</td><td>true</td><td>Optional</td><td>Whether to ignore threads when retaining messages or not.</td></tr><tr><td>retentionOverrideGlobal</td><td>true</td><td>Optional</td><td>Whether to override the global retention settings for the room or not.</td></tr><tr><td>encrypted</td><td>true</td><td>Optional</td><td>Whether the room is encrypted or not.</td></tr><tr><td>favorite</td><td>{ "favorite": true, "defaultValue": false }</td><td>Optional</td><td>The favorite settings of the room. Whether the room is marked as favorite and whether it is set as the default room.</td></tr></tbody></table>

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
