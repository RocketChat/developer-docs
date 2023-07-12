---
description: Get push notification for a message
---

# Get push notification

{% hint style="info" %}
Requires the `can-access-room` permission.
{% endhint %}

| URL                | Requires Auth | HTTP Method |
| ------------------ | ------------- | ----------- |
| `/api/v1/push.get` | `yes`         | `GET`       |

## Query Parameters

| Argument | Example             | Required | Description     |
| -------- | ------------------- | -------- | --------------- |
| `id`     | `WkbwSntxt8D3jLp8G` | Required | The message id. |

## Example Call

{% tabs %}
{% tab title="Curl" %}
```
curl -L -X GET 'http://localhost:3000/api/v1/push.get?id=WkbwSntxt8D3jLp8G' \
-H 'X-User-Id: d26x6zSkaPSe5gCyy' \
-H 'X-Auth-Token: Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92'
```
{% endtab %}

{% tab title="Node.js" %}
```
var request = require('request');
var options = {
  'method': 'GET',
  'url': 'http://localhost:3000/api/v1/push.get?id=WkbwSntxt8D3jLp8G',
  'headers': {
    'X-User-Id': 'd26x6zSkaPSe5gCyy',
    'X-Auth-Token': 'Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92'
  }
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

url = "http://localhost:3000/api/v1/push.get?id=WkbwSntxt8D3jLp8G"

payload={}
headers = {
  'X-User-Id': 'd26x6zSkaPSe5gCyy',
  'X-Auth-Token': 'Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92'
}

response = requests.request("GET", url, headers=headers, data=payload)

print(response.text)
```
{% endtab %}

{% tab title="PHP" %}
```
<?php
require_once 'HTTP/Request2.php';
$request = new HTTP_Request2();
$request->setUrl('http://localhost:3000/api/v1/push.get?id=WkbwSntxt8D3jLp8G');
$request->setMethod(HTTP_Request2::METHOD_GET);
$request->setConfig(array(
  'follow_redirects' => TRUE
));
$request->setHeader(array(
  'X-User-Id' => 'd26x6zSkaPSe5gCyy',
  'X-Auth-Token' => 'Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92'
));
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
HttpResponse<String> response = Unirest.get("http://localhost:3000/api/v1/push.get?id=WkbwSntxt8D3jLp8G")
  .header("X-User-Id", "d26x6zSkaPSe5gCyy")
  .header("X-Auth-Token", "Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92")
  .asString();
```
{% endtab %}
{% endtabs %}

## Example Result

### Success

```javascript
{
    "data": {
        "message": {
            "_id": "WkbwSntxt8D3jLp8G",
            "rid": "iu7jtPAhvEeAS5tNq",
            "msg": "fsfs",
            "ts": "2021-10-22T14:29:23.581Z",
            "u": {
                "_id": "d26x6zSkaPSe5gCyy",
                "username": "rodriq",
                "name": "Rodriq"
            },
            "urls": [],
            "mentions": [],
            "channels": [],
            "md": [
                {
                    "type": "PARAGRAPH",
                    "value": [
                        {
                            "type": "PLAIN_TEXT",
                            "value": "fsfs"
                        }
                    ]
                }
            ],
            "_updatedAt": "2021-10-22T14:29:23.603Z"
        },
        "notification": {
            "from": "push",
            "badge": 2,
            "sound": "default",
            "priority": 10,
            "title": "#vb",
            "text": "rodriq: fsfs",
            "payload": {
                "host": "http://localhost:3000/",
                "messageId": "WkbwSntxt8D3jLp8G",
                "notificationType": "message",
                "rid": "iu7jtPAhvEeAS5tNq",
                "sender": {
                    "_id": "d26x6zSkaPSe5gCyy",
                    "username": "rodriq",
                    "name": "Rodriq"
                },
                "senderName": "rodriq",
                "type": "c",
                "name": "vb"
            },
            "userId": "d26x6zSkaPSe5gCyy",
            "notId": 654494840,
            "gcm": {
                "style": "inbox",
                "image": "http://localhost:3000/images/logo/android-chrome-192x192.png"
            },
            "apn": {
                "category": "MESSAGE"
            }
        }
    },
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **Message not Found**: Seen when the room id passed in does not exist.
* **Not Allowed**: Occurs when the user doesn't have access to the room.
* **Room not Found**: Occurs when the room containing the message is not found.

{% tabs %}
{% tab title=" Authorization" %}
```javascript
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}

{% tab title="Message not Found" %}
```
{
    "success": false,
    "error": "error-message-not-found"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| `3.5.0` | Added       |
