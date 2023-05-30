# Get Current Import Operations

{% hint style="info" %}
Requires the `Run Import` permission.
{% endhint %}

| URL                                 | Requires Auth | HTTP Method |
| ----------------------------------- | ------------- | ----------- |
| `/api/v1/getCurrentImportOperation` | `yes`         | `GET`       |

## Example Call

{% tabs %}
{% tab title="Curl" %}
```
curl -L -X GET 'http://localhost:3000/api/v1/getCurrentImportOperation' \
-H 'X-User-Id: d26x6zSkaPSe5gCyy' \
-H 'X-Auth-Token: Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92'
```
{% endtab %}

{% tab title="Node.js" %}
```
var request = require('request');
var options = {
  'method': 'GET',
  'url': 'http://localhost:3000/api/v1/getCurrentImportOperation',
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

url = "http://localhost:3000/api/v1/getCurrentImportOperation"

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
$request->setUrl('http://localhost:3000/api/v1/getCurrentImportOperation');
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
HttpResponse<String> response = Unirest.get("http://localhost:3000/api/v1/getCurrentImportOperation")
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
    "success": true,
    "operation": {
        "_id": "7PbvsnKJD9ZAqw38C",
        "type": "Pending Avatars",
        "importerKey": "pending-avatars",
        "ts": 1635337234169,
        "status": "importer_done",
        "valid": true,
        "user": "d26x6zSkaPSe5gCyy",
        "_updatedAt": "2021-10-27T12:20:34.184Z"
    }
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.

{% tabs %}
{% tab title=" Authorization" %}
```javascript
{
    "success": false,
    "error": "unauthorized"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| `3.0.0` | Added       |
