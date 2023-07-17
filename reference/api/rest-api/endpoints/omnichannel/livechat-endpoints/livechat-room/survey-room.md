# Survey Room

Survey on a Livechat room.

| URL                            | Requires Auth | HTTP Method |
| ------------------------------ | ------------- | ----------- |
| `/api/v1/livechat/room.survey` | `no`          | `POST`      |

## Payload <a href="#payload" id="payload"></a>

<table data-header-hidden><thead><tr><th width="141">Argument</th><th width="261">Example</th><th>Required</th><th>Description</th></tr></thead><tbody><tr><td><code>rid</code></td><td><code>JZ8Y2dLfYhsg323R</code></td><td>Required</td><td>The room Id.</td></tr><tr><td><code>token</code></td><td><code>d4a8338e5a7d98b6750b4f839431b34a3f4813b2c43f7d89597948f21f607bb4</code></td><td>Required</td><td>The visitor token</td></tr><tr><td><code>data</code></td><td><code>"data": [ { "name": "additionalFeedback", "value": "Thankszzzzz" } ]</code></td><td>Required</td><td>An array of object with <code>name</code> and <code>value</code></td></tr></tbody></table>

## Example Call <a href="#example-payload" id="example-payload"></a>

{% tabs %}
{% tab title="Curl" %}
```bash
curl --location --request POST 'http://localhost:3000/api/v1/livechat/room.survey' \
--header 'Content-type: application/json' \
--header 'X-Auth-Token: tnuxBeGR7axX27zfRsch2a8cksBHnSJMIxJ-yvgv_9r' \
--header 'X-User-Id: Dtx5kwoQJGYQSw3Qh' \
--data-raw '{
    "rid": "gMMeBpWyLeowCrzBv",
    "token": "d4a8338e5a7d98b6750b4f839431b34a3f4813b2c43f7d89597948f21f607bb4",
    "data": [
        {
            "name": "additionalFeedback",
            "value": "Thankszzzzz"
        } 
    ]
}'
```
{% endtab %}

{% tab title="Node.js" %}
```javascript
var request = require('request');
var options = {
  'method': 'POST',
  'url': 'http://localhost:3000/api/v1/livechat/room.survey',
  'headers': {
    'Content-type': 'application/json',
    'X-Auth-Token': 'tnuxBeGR7axX27zfRsch2a8cksBHnSJMIxJ-yvgv_9r',
    'X-User-Id': 'Dtx5kwoQJGYQSw3Qh'
  },
  body: JSON.stringify({
    "rid": "gMMeBpWyLeowCrzBv",
    "token": "d4a8338e5a7d98b6750b4f839431b34a3f4813b2c43f7d89597948f21f607bb4",
    "data": [
      {
        "name": "additionalFeedback",
        "value": "Thankszzzzz"
      }
    ]
  })

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

url = "http://localhost:3000/api/v1/livechat/room.survey"

payload = json.dumps({
  "rid": "gMMeBpWyLeowCrzBv",
  "token": "d4a8338e5a7d98b6750b4f839431b34a3f4813b2c43f7d89597948f21f607bb4",
  "data": [
    {
      "name": "additionalFeedback",
      "value": "Thankszzzzz"
    }
  ]
})
headers = {
  'Content-type': 'application/json',
  'X-Auth-Token': 'tnuxBeGR7axX27zfRsch2a8cksBHnSJMIxJ-yvgv_9r',
  'X-User-Id': 'Dtx5kwoQJGYQSw3Qh'
}

response = requests.request("POST", url, headers=headers, data=payload)

print(response.text)

```
{% endtab %}
{% endtabs %}

## Example Result

### Success

```json
{
    "rid": "gMMeBpWyLeowCrzBv",
    "data": {
        "additionalFeedback": "Thankszzzzz"
    },
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Invalid token**: When the visitor token provided is invalid.
* **Invalid Room**: Occurs when the given `rid` is invalid.

{% tabs %}
{% tab title=" Invalid token" %}
```javascript
{
    "success": false,
    "error": "[invalid-token]",
    "errorType": "invalid-token"
}
```
{% endtab %}
{% endtabs %}
