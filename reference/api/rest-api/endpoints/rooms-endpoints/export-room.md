---
description: Export room to a file or email.
---

# Export Room

{% hint style="info" %}
This requires the user to have the `mail-messages` permission.
{% endhint %}

| URL                    | Requires Auth | HTTP Method |
| ---------------------- | ------------- | ----------- |
| `/api/v1/rooms.export` | `yes`         | `POST`      |

## Payload

| Argument   | Example              | Required | Description                           |
| ---------- | -------------------- | -------- | ------------------------------------- |
| `rid`      | `JZ8Y2dLfYhsg323Rf`  | Required | The room Id.                          |
| `type`     | `email` or `file`    | Required | How you want the room to be exported. |
| `dateFrom` | `2020-01-13`         | Optional | Startdate to begin fetching.          |
| `dateTo`   | `2021-12-13`         | Optional | End date for fetching.                |
| `format`   | `html` or `json`     | Required | The file type to export as.           |

### Example Payload

```
{
    "rid": "iu7jtPAhvEeAS5tNq",
    "type": "file",
    "dateFrom": "2000-01-01",
    "dateTo": "2021-11-25",
    "format": "html"
}
```

## Example Call

{% tabs %}
{% tab title="Curl" %}
```
curl -L -X POST 'http://localhost:3000/api/v1/rooms.export' \
-H 'X-User-Id: d26x6zSkaPSe5gCyy' \
-H 'X-Auth-Token: Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92' \
-H 'Content-Type: application/json' \
--data-raw '{
    "rid": "iu7jtPAhvEeAS5tNq",
    "type": "file",
    "dateFrom": "2000-01-01",
    "dateTo": "2021-11-25",
    "format": "html"
}'
```
{% endtab %}

{% tab title="Node.js" %}
```
var request = require('request');
var options = {
  'method': 'POST',
  'url': 'http://localhost:3000/api/v1/rooms.export',
  'headers': {
    'X-User-Id': 'd26x6zSkaPSe5gCyy',
    'X-Auth-Token': 'Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({"rid":"iu7jtPAhvEeAS5tNq","type":"file","dateFrom":"2000-01-01","dateTo":"2021-11-25","format":"html"})

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

url = "http://localhost:3000/api/v1/rooms.export"

payload="{\n    \"rid\": \"iu7jtPAhvEeAS5tNq\",\n    \"type\": \"file\",\n    \"dateFrom\": \"2000-01-01\",\n    \"dateTo\": \"2021-11-25\",\n    \"format\": \"html\"\n}"
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
$request->setUrl('http://localhost:3000/api/v1/rooms.export');
$request->setMethod(HTTP_Request2::METHOD_POST);
$request->setConfig(array(
  'follow_redirects' => TRUE
));
$request->setHeader(array(
  'X-User-Id' => 'd26x6zSkaPSe5gCyy',
  'X-Auth-Token' => 'Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92',
  'Content-Type' => 'application/json'
));
$request->setBody('{\n    "rid": "iu7jtPAhvEeAS5tNq",\n    "type": "file",\n    "dateFrom": "2000-01-01",\n    "dateTo": "2021-11-25",\n    "format": "html"\n}');
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
HttpResponse<String> response = Unirest.post("http://localhost:3000/api/v1/rooms.export")
  .header("X-User-Id", "d26x6zSkaPSe5gCyy")
  .header("X-Auth-Token", "Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92")
  .header("Content-Type", "application/json")
  .body("{\n    \"rid\": \"iu7jtPAhvEeAS5tNq\",\n    \"type\": \"file\",\n    \"dateFrom\": \"2000-01-01\",\n    \"dateTo\": \"2021-11-25\",\n    \"format\": \"html\"\n}")
  .asString();
```
{% endtab %}
{% endtabs %}

## Example Result

### Success

```javascript
{
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **Invalid Params**: Occurs when one or more needed parameters are missing.
* **Invalid Room**: Occurs when the given `rid` is invalid.
* **Not Allowed**: Occurs when the user lacks the `mail-messages` permission and doesn't have access to the room.
* **Invalid Format**: Occurs when the export format is not specified

{% tabs %}
{% tab title=" Authorization" %}
```javascript
{
    "success": false,
    "error": "unauthorized"
}
```
{% endtab %}

{% tab title="Invalid Params" %}
```
{
    "success": false,
    "error": "[error-invalid-params]",
    "errorType": "error-invalid-params"
}
```
{% endtab %}

{% tab title="Invalid Room ID" %}
```
{
    "success": false,
    "error": "[error-invalid-room]",
    "errorType": "error-invalid-room"
}
```
{% endtab %}

{% tab title="Invalid Format" %}
```json
{
    "success": false,
    "error": "[error-invalid-format]",
    "errorType": "error-invalid-format"
}
```
{% endtab %}
{% endtabs %}

| Version | Description |
| ------- | ----------- |
| 3.8.0   | Added       |

