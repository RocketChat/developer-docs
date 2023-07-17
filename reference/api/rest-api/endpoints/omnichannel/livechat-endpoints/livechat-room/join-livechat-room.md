# Join Livechat Room

Call this endpoint to join a Live chat room.

{% hint style="info" %}
This requires the `view-l-room` permission.
{% endhint %}

| URL                          | Requires Auth | HTTP Method |
| ---------------------------- | ------------- | ----------- |
| `/api/v1/livechat/room.join` | `yes`         | `GET`       |

## Query Parameters

<table><thead><tr><th width="139">Argument</th><th>Example</th><th width="176">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code></td><td><code>gMMeBpWyLeowCrzBv</code></td><td>Required</td><td>Id of the Livechat room to join</td></tr></tbody></table>

## Example Call

{% tabs %}
{% tab title="Curl" %}
```bash
curl --location --request GET 'http://localhost:3000/api/v1/livechat/room.join?roomId=gMMeBpWyLeowCrzBv' \
--header 'Content-type: application/json' \
--header 'X-Auth-Token: OsLBoPh6cUgNuh6mWT8z4VIY_nGl8R30XVE4QNDLT6S' \
--header 'X-User-Id: f5vPj6jfkRXipkwoC' \
--data-raw ''
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
var request = require('request');
var options = {
  'method': 'GET',
  'url': 'http://localhost:3000/api/v1/livechat/room.join?roomId=gMMeBpWyLeowCrzBv',
  'headers': {
    'Content-type': 'application/json',
    'X-Auth-Token': 'OsLBoPh6cUgNuh6mWT8z4VIY_nGl8R30XVE4QNDLT6S',
    'X-User-Id': 'f5vPj6jfkRXipkwoC'
  }
};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});

```
{% endtab %}

{% tab title="Python" %}
```python
import requests
import json

url = "http://localhost:3000/api/v1/livechat/room.join?roomId=gMMeBpWyLeowCrzBv"

payload = ""
headers = {
  'Content-type': 'application/json',
  'X-Auth-Token': 'OsLBoPh6cUgNuh6mWT8z4VIY_nGl8R30XVE4QNDLT6S',
  'X-User-Id': 'f5vPj6jfkRXipkwoC'
}

response = requests.request("GET", url, headers=headers, data=payload)

print(response.text)

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
* **Missing key**: This error is thrown when the `roomId` field is not supplied.
* **Invalid Room**: Occurs when the given `roomId` is invalid.
* **Not allowed**: Occurs when the authenticated user doesn't have permission to access the room.

{% tabs %}
{% tab title=" Authorization" %}
```javascript
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}

{% tab title="Missing Key" %}
```json
{
    "message": "Match error: Missing key 'roomId'",
    "path": "",
    "sanitizedError": {
        "isClientSafe": true,
        "error": 400,
        "reason": "Match failed",
        "message": "Match failed [400]",
        "errorType": "Meteor.Error"
    },
    "errorType": "Match.Error",
    "success": false
}n
```
{% endtab %}

{% tab title="Invalid Room ID" %}
```json
{
    "isClientSafe": true,
    "error": "error-invalid-room",
    "reason": "Invalid room",
    "details": {
        "method": "joinRoom"
    },
    "message": "Invalid room [error-invalid-room]",
    "errorType": "Meteor.Error",
    "success": false
}
```
{% endtab %}
{% endtabs %}
