---
description: Sets the encryption for a group.
---

# Group Set Encrypted

| URL                           | Requires Auth | HTTP Method |
| ----------------------------- | ------------- | ----------- |
| `/api/v1/groups.setEncrypted` | Yes           | POST        |

## Payload

| Argument               | Example                           | Required | Description                                          |
| ---------------------- | --------------------------------- | -------- | ---------------------------------------------------- |
| `encrypted`            | `true`                            | Required | Whether or not to encrypt the room.                  |
| `roomID` or `roomName` | `JZ8Y2dLfYhsg323Rf` or `My Group` | Required | The group id or name on which to set the encryption. |

### Example Payload

```
{
    "encrypted": false,
    "roomId": "JZ8Y2dLfYhsg323Rf"
}
```

## Example Call

{% tabs %}
{% tab title="Curl" %}
```
curl -L -X POST 'http://localhost:3000/api/v1/groups.setEncrypted' \
-H 'X-User-Id: d26x6zSkaPSe5gCyy' \
-H 'X-Auth-Token: Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92' \
-H 'Content-Type: application/json' \
--data-raw '{
    "encrypted": false,
    "roomId": "JZ8Y2dLfYhsg323Rf"
}'
```
{% endtab %}

{% tab title="Node.js" %}
```
var request = require('request');
var options = {
  'method': 'POST',
  'url': 'http://localhost:3000/api/v1/groups.setEncrypted',
  'headers': {
    'X-User-Id': 'd26x6zSkaPSe5gCyy',
    'X-Auth-Token': 'Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({"encrypted":false,"roomId":"JZ8Y2dLfYhsg323Rf"})

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

url = "http://localhost:3000/api/v1/groups.setEncrypted"

payload="{\n    \"encrypted\": false,\n    \"roomId\": \"JZ8Y2dLfYhsg323Rf\"\n}"
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
$request->setUrl('http://localhost:3000/api/v1/groups.setEncrypted');
$request->setMethod(HTTP_Request2::METHOD_POST);
$request->setConfig(array(
  'follow_redirects' => TRUE
));
$request->setHeader(array(
  'X-User-Id' => 'd26x6zSkaPSe5gCyy',
  'X-Auth-Token' => 'Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92',
  'Content-Type' => 'application/json'
));
$request->setBody('{\n    "encrypted": false,\n    "roomId": "JZ8Y2dLfYhsg323Rf"\n}');
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
HttpResponse<String> response = Unirest.post("http://localhost:3000/api/v1/groups.setEncrypted")
  .header("X-User-Id", "d26x6zSkaPSe5gCyy")
  .header("X-Auth-Token", "Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92")
  .header("Content-Type", "application/json")
  .body("{\n    \"encrypted\": false,\n    \"roomId\": \"JZ8Y2dLfYhsg323Rf\"\n}")
  .asString();
```
{% endtab %}
{% endtabs %}

## Example Result

### Success

```javascript
{
    "group": {
        "_id": "JZ8Y2dLfYhsg323Rf",
        "fname": "test",
        "description": "",
        "broadcast": false,
        "encrypted": false,
        "teamMain": true,
        "name": "test",
        "t": "p",
        "msgs": 0,
        "usersCount": 1,
        "u": {
            "_id": "d26x6zSkaPSe5gCyy",
            "username": "rodriq"
        },
        "ts": "2021-10-22T11:59:17.029Z",
        "ro": false,
        "teamId": "6172a795c563fc000acc4629",
        "_updatedAt": "2021-10-22T12:00:11.496Z"
    },
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **No encrypted parameter**: Occurs when the endpoint is called without the encrypted body param.
* **No Room Id or roomName**: Occurs when no `roomID or roomName` is given.
* **Invalid Room**: Occurs when the given `room` is invalid.

{% tabs %}
{% tab title=" Authorization" %}
```javascript
{
    "success": false,
    "error": "unauthorized"
}
```
{% endtab %}

{% tab title="No Room Id or Name" %}
```
{
    "success": false,
    "error": "The parameter \"roomId\" or \"roomName\" is required [error-room-param-not-provided]",
    "errorType": "error-room-param-not-provided"
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
