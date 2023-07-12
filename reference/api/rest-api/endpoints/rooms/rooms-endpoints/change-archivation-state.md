---
description: Change the Archive state of a room.
---

# Change Archivation State

| URL                                    | Requires Auth | HTTP Method |
| -------------------------------------- | ------------- | ----------- |
| `/api/v1/rooms.changeArchivationState` | `yes`         | `POST`      |

## Payload

| Argument | Example            | Required | Description                                                     |
| -------- | ------------------ | -------- | --------------------------------------------------------------- |
| `rid`    | `JZ8Y2dLfYhsg323R` | Required | The room Id.                                                    |
| `action` | `archive`          | Optional | When passed in, the room will be archived otherwise unarchived. |

### Example Payload

```json
{
    "rid": "iu7jtPAhvEeAS5tNq",
    "action": "archive"
}
```

## Example Call

{% tabs %}
{% tab title="Curl" %}
```
curl -L -X POST 'http://localhost:3000/api/v1/rooms.changeArchivationState' \
-H 'X-User-Id: d26x6zSkaPSe5gCyy' \
-H 'X-Auth-Token: Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92' \
-H 'Content-Type: application/json' \
--data-raw '{
    "rid": "iu7jtPAhvEeAS5tNq",
    "action": "archive"
}'
```
{% endtab %}

{% tab title="Node.js" %}
```
var request = require('request');
var options = {
  'method': 'POST',
  'url': 'http://localhost:3000/api/v1/rooms.changeArchivationState',
  'headers': {
    'X-User-Id': 'd26x6zSkaPSe5gCyy',
    'X-Auth-Token': 'Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({"rid":"iu7jtPAhvEeAS5tNq","action":"archive"})

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

url = "http://localhost:3000/api/v1/rooms.changeArchivationState"

payload="{\n    \"rid\": \"iu7jtPAhvEeAS5tNq\",\n    \"action\": \"archive\"\n}"
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
$request->setUrl('http://localhost:3000/api/v1/rooms.changeArchivationState');
$request->setMethod(HTTP_Request2::METHOD_POST);
$request->setConfig(array(
  'follow_redirects' => TRUE
));
$request->setHeader(array(
  'X-User-Id' => 'd26x6zSkaPSe5gCyy',
  'X-Auth-Token' => 'Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92',
  'Content-Type' => 'application/json'
));
$request->setBody('{\n    "rid": "iu7jtPAhvEeAS5tNq",\n    "action": "archive"\n}');
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
HttpResponse<String> response = Unirest.post("http://localhost:3000/api/v1/rooms.changeArchivationState")
  .header("X-User-Id", "d26x6zSkaPSe5gCyy")
  .header("X-Auth-Token", "Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92")
  .header("Content-Type", "application/json")
  .body("{\n    \"rid\": \"iu7jtPAhvEeAS5tNq\",\n    \"action\": \"archive\"\n}")
  .asString();
```
{% endtab %}
{% endtabs %}

## Example Result

### Success

```json
{
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
    "error": "Invalid room [error-invalid-room]",
    "errorType": "error-invalid-room",
    "details": {
        "method": "unarchiveRoom"
    }
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 3.3.0   | Added       |
