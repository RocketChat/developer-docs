---
description: Sets the end-to-end encryption key ID for a room
---

# Set Room E2E key

| URL                        | Requires Auth | HTTP Method |
| -------------------------- | ------------- | ----------- |
| `/api/v1/e2e.setRoomKeyID` | `Yes`         | `POST`      |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Payload

| Argument | Example             | Required | Description              |
| -------- | ------------------- | -------- | ------------------------ |
| `rid`    | `Qe3Wa3outaDMKzAZC` | Required | The Room Id              |
| `keyID`  | `my-UniQu3_ke4_Id`  | Required | The key you wish to set. |

### Example Payload

```
{
    "rid": "Qe3Wa3outaDMKzAZC",
    "keyID": "my-UniQu3_ke4_Id"
}
```

## Example Call

{% tabs %}
{% tab title="Curl" %}
```
curl --location --request POST 'http://localhost:3000/api/v1/e2e.setRoomKeyID' \
--header 'X-User-Id: d26x6zSkaPSe5gCyy' \
--header 'X-Auth-Token: Di9OKWzdu7V2vW3lHO0oYLOOr6P2Y0n9zQlx20qn2cU' \
--header 'Content-Type: application/json' \
--data-raw '{
    "rid": "wCiXndNp5NqNY3uCc",
    "keyID": "my-UniQu3_ke4_Id"
}'
```
{% endtab %}

{% tab title="Node.js" %}
```
var request = require('request');
var options = {
  'method': 'POST',
  'url': 'http://localhost:3000/api/v1/e2e.setRoomKeyID',
  'headers': {
    'X-User-Id': 'd26x6zSkaPSe5gCyy',
    'X-Auth-Token': 'Di9OKWzdu7V2vW3lHO0oYLOOr6P2Y0n9zQlx20qn2cU',
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({"rid":"wCiXndNp5NqNY3uCc","keyID":"my-UniQu3_ke4_Id"})

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

url = "http://localhost:3000/api/v1/e2e.setRoomKeyID"

payload="{\n    \"rid\": \"wCiXndNp5NqNY3uCc\",\n    \"keyID\": \"my-UniQu3_ke4_Id\"\n}"
headers = {
  'X-User-Id': 'd26x6zSkaPSe5gCyy',
  'X-Auth-Token': 'Di9OKWzdu7V2vW3lHO0oYLOOr6P2Y0n9zQlx20qn2cU',
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
$request->setUrl('http://localhost:3000/api/v1/e2e.setRoomKeyID');
$request->setMethod(HTTP_Request2::METHOD_POST);
$request->setConfig(array(
  'follow_redirects' => TRUE
));
$request->setHeader(array(
  'X-User-Id' => 'd26x6zSkaPSe5gCyy',
  'X-Auth-Token' => 'Di9OKWzdu7V2vW3lHO0oYLOOr6P2Y0n9zQlx20qn2cU',
  'Content-Type' => 'application/json'
));
$request->setBody('{\n    "rid": "wCiXndNp5NqNY3uCc",\n    "keyID": "my-UniQu3_ke4_Id"\n}');
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
HttpResponse<String> response = Unirest.post("http://localhost:3000/api/v1/e2e.setRoomKeyID")
  .header("X-User-Id", "d26x6zSkaPSe5gCyy")
  .header("X-Auth-Token", "Di9OKWzdu7V2vW3lHO0oYLOOr6P2Y0n9zQlx20qn2cU")
  .header("Content-Type", "application/json")
  .body("{\n    \"rid\": \"wCiXndNp5NqNY3uCc\",\n    \"keyID\": \"my-UniQu3_ke4_Id\"\n}")
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
* **No Room Id**: Occurs when no `rid` is given.
* **Invalid Room**: Occurs when the given `rid` is invalid.
* **Key already Exists**: Happens when the Room in request already has an E2E key set.

{% tabs %}
{% tab title=" Authorization" %}
```javascript
{
    "success": false,
    "error": "unauthorized"
}
```
{% endtab %}

{% tab title="No Room Id" %}
```
{
    "success": false,
    "error": "Match error: Expected string, got undefined"
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
        "method": "canAccessRoom"
    }
}
```
{% endtab %}

{% tab title="Key Already Exists" %}
```
{
    "success": false,
    "error": "E2E Key ID already exists [error-room-e2e-key-already-exists]",
    "errorType": "error-room-e2e-key-already-exists",
    "details": {
        "method": "e2e.setRoomKeyID"
    }
}
```
{% endtab %}
{% endtabs %}
