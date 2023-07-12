---
description: Convert a private group to a team.
---

# Group convertToTeam

|                                | Requires Auth | Method |
| ------------------------------ | ------------- | ------ |
| `/api/v1/groups.convertToTeam` | Yes           | POST   |

## Payload

| Argument               | Example                           | Required | Description                                       |
| ---------------------- | --------------------------------- | -------- | ------------------------------------------------- |
| `roomID` or `roomName` | `JZ8Y2dLfYhsg323Rf` or `My Group` | Required | The name or id of the group to convert to a team. |

### Example Payload

```
{
    "roomId": "JZ8Y2dLfYhsg323Rf"
}
```

## Example Call

{% tabs %}
{% tab title="Curl" %}
```
curl -L -X POST 'http://localhost:3000/api/v1/groups.convertToTeam' \
-H 'X-User-Id: d26x6zSkaPSe5gCyy' \
-H 'X-Auth-Token: Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92' \
-H 'Content-Type: application/json' \
--data-raw '{
    "roomId": "h3HLZkQdrWCPg2RN7"
}'
```
{% endtab %}

{% tab title="Node.js" %}
```
var request = require('request');
var options = {
  'method': 'POST',
  'url': 'http://localhost:3000/api/v1/groups.convertToTeam',
  'headers': {
    'X-User-Id': 'd26x6zSkaPSe5gCyy',
    'X-Auth-Token': 'Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({"roomId":"h3HLZkQdrWCPg2RN7"})

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

url = "http://localhost:3000/api/v1/groups.convertToTeam"

payload="{\n    \"roomId\": \"h3HLZkQdrWCPg2RN7\"\n}"
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
$request->setUrl('http://localhost:3000/api/v1/groups.convertToTeam');
$request->setMethod(HTTP_Request2::METHOD_POST);
$request->setConfig(array(
  'follow_redirects' => TRUE
));
$request->setHeader(array(
  'X-User-Id' => 'd26x6zSkaPSe5gCyy',
  'X-Auth-Token' => 'Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92',
  'Content-Type' => 'application/json'
));
$request->setBody('{\n    "roomId": "h3HLZkQdrWCPg2RN7"\n}');
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
HttpResponse<String> response = Unirest.post("http://localhost:3000/api/v1/groups.convertToTeam")
  .header("X-User-Id", "d26x6zSkaPSe5gCyy")
  .header("X-Auth-Token", "Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92")
  .header("Content-Type", "application/json")
  .body("{\n    \"roomId\": \"h3HLZkQdrWCPg2RN7\"\n}")
  .asString();
```
{% endtab %}
{% endtabs %}

## Example Result

### Success

```javascript
{
    "team": {
        "_id": "6172b15bc563fc000acc462e",
        "name": "ddd",
        "type": 1,
        "createdAt": "2021-10-22T12:40:59.928Z",
        "createdBy": {
            "_id": "d26x6zSkaPSe5gCyy",
            "username": "rodriq"
        },
        "_updatedAt": "2021-10-22T12:40:59.928Z",
        "roomId": "h3HLZkQdrWCPg2RN7"
    },
    "success": true
}
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **Already Exists**: Senn when the team already exists.
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

{% tab title="Already Exists" %}
```
{
    "success": false,
    "error": "team-name-already-exists"
}
```
{% endtab %}

{% tab title="No roomID or roomName" %}
```
{
    "success": false,
    "error": "The parameter \"roomId\" or \"roomName\" is required"
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
