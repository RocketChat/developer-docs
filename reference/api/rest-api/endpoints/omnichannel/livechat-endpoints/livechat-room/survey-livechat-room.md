# Survey Livechat Room

Provide feedback on a Livechat room.

<table><thead><tr><th width="163">HTTP Method</th><th width="338">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/livechat/room.survey</code></td><td><code>no</code></td></tr></tbody></table>

## Body <a href="#payload" id="payload"></a>

<table><thead><tr><th width="141">Key</th><th width="288">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>rid</code><mark style="color:red;"><code>*</code></mark></td><td><code>JZ8Y2dLfYhsg323R</code></td><td>The room ID.</td></tr><tr><td><code>token</code><mark style="color:red;"><code>*</code></mark></td><td><code>d4a8338e5a7d98b6750b4f839431b34a3f4813b2c43f7d89597948f21f607bb4</code></td><td>The visitor token.</td></tr><tr><td><code>data</code><mark style="color:red;"><code>*</code></mark></td><td><p><code>"data": [ {</code> </p><p><code>"name": "additionalFeedback", "value": "Thankszzzzz" } ]</code></p></td><td>An array of object with <code>name</code> and <code>value</code> to provide feedback.</td></tr></tbody></table>

## Example Call <a href="#example-payload" id="example-payload"></a>

```powershell
curl --location --request POST 'http://localhost:3000/api/v1/livechat/room.survey' \
--header 'Content-type: application/json' \
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

## Example Response

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
```json
{
    "success": false,
    "error": "[invalid-token]",
    "errorType": "invalid-token"
}
```
{% endtab %}
{% endtabs %}
