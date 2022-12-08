# Get Latest Import Operations

| URL                                 | Requires Auth | HTTP Method |
| ----------------------------------- | ------------- | ----------- |
| `/api/v1/getLatestImportOperations` | `yes`         | `GET`       |

## Example Call

{% tabs %}
{% tab title="Curl" %}
```
curl -L -X GET 'http://localhost:3000/api/v1/getLatestImportOperations' \
-H 'X-User-Id: d26x6zSkaPSe5gCyy' \
-H 'X-Auth-Token: Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92'
```
{% endtab %}

{% tab title="Node.js" %}
```
var request = require('request');
var options = {
  'method': 'GET',
  'url': 'http://localhost:3000/api/v1/getLatestImportOperations',
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

url = "http://localhost:3000/api/v1/getLatestImportOperations"

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
$request->setUrl('http://localhost:3000/api/v1/getLatestImportOperations');
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
HttpResponse<String> response = Unirest.get("http://localhost:3000/api/v1/getLatestImportOperations")
  .header("X-User-Id", "d26x6zSkaPSe5gCyy")
  .header("X-Auth-Token", "Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92")
  .asString();
```
{% endtab %}
{% endtabs %}

## Example Result

### Success

```javascript
[
    {
        "_id": "MJxTRZsYdho8Ww2qq",
        "type": "Pending Avatars",
        "importerKey": "pending-avatars",
        "ts": 1635280600083,
        "status": "importer_user_selection",
        "valid": false,
        "user": "d26x6zSkaPSe5gCyy",
        "_updatedAt": "2021-10-27T11:26:24.430Z"
    },
    {
        "_id": "YzSCu9WgqJ3wutF4T",
        "type": "Pending Files",
        "importerKey": "pending-files",
        "ts": 1635280596592,
        "status": "importer_done",
        "valid": false,
        "user": "d26x6zSkaPSe5gCyy",
        "_updatedAt": "2021-10-27T08:32:42.609Z"
    },
    {
        "_id": "96WJDaxXpwXC3fTD5",
        "type": "Pending Files",
        "importerKey": "pending-files",
        "ts": 1635277590992,
        "status": "importer_user_selection",
        "valid": false,
        "user": "d26x6zSkaPSe5gCyy",
        "_updatedAt": "2021-10-27T08:32:42.609Z"
    },
    {
        "_id": "zYc5kuFRaszfqCegB",
        "type": "Pending Avatars",
        "importerKey": "pending-avatars",
        "ts": 1635277492185,
        "status": "importer_done",
        "valid": false,
        "user": "d26x6zSkaPSe5gCyy",
        "_updatedAt": "2021-10-27T08:32:42.609Z"
    },
    {
        "_id": "XckCNn9ZsdywHso4f",
        "type": "Pending Avatars",
        "importerKey": "pending-avatars",
        "ts": 1635277452755,
        "status": "importer_done",
        "valid": false,
        "user": "d26x6zSkaPSe5gCyy",
        "_updatedAt": "2021-10-27T08:32:42.609Z"
    },
    {
        "_id": "NRqiLZ4bADfGwMRMz",
        "type": "CSV",
        "importerKey": "csv",
        "ts": 1635247067385,
        "status": "importer_file_loaded",
        "valid": false,
        "user": "d26x6zSkaPSe5gCyy",
        "_updatedAt": "2021-10-27T08:32:42.609Z",
        "contentType": "image/svg+xml",
        "file": "2021926111747_d26x6zSkaPSe5gCyy_pp.svg"
    },
    {
        "_id": "9mCbRPTbF9QHQ3RM6",
        "type": "Pending Avatars",
        "importerKey": "pending-avatars",
        "ts": 1635247489080,
        "status": "importer_done",
        "valid": false,
        "user": "d26x6zSkaPSe5gCyy",
        "_updatedAt": "2021-10-27T08:32:42.609Z"
    }
]
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
| `1.0.0` | Added       |
