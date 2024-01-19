---
description: Retrieves Users Of Room Without E2E Key
---

# Get Users Of Room Without E2E Key

| URL                                   | Requires Auth                            | HTTP Method |
| ------------------------------------- | ---------------------------------------- | ----------- |
| `api/v1/e2e.getUsersOfRoomWithoutKey` | [`YES`](../../authentication-endpoints/) | `GET`       |

## Query Parameters

<table><thead><tr><th width="146">Argument</th><th>Example</th><th width="161">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>rid</code></td><td><code>zRAeTszXor8CCPceB</code></td><td>Required</td><td>The room <code>_id</code>.</td></tr></tbody></table>

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/e2e.getUsersOfRoomWithoutKey\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Example Response

### Success

```json
{
    "users": [
        {
            "_id": "XycfA5CetCPuEjqxw",
            "e2e": {
                "public_key": "{\"alg\":\"RSA-OAEP-256\",\"e\":\"AQAB\",\"ext\":true,\"key_ops\":[\"encrypt\"],\"kty\":\"RSA\",\"n\":\"oMO9ydjRxD3JzcAgMvyBZAc_pIOBIxOLVUChZ8mB3JNtLREC751hHT-WPZVZquWA6X4CihHejFfpIyAD_w-0MIToudTGO-f1aeE4Wc9-SBKjSQPphCuZMTwZ7iRtfUwHeGy5yM94uQPp07sEi9BmJSZqHscHc-6G520MyBhNU6uznQf-Sp85Q4etl4Ifs09khM-VMnBqKwh2QJx8w0880Vc3Zufve6udg0aSQ\"}"
            }
        }
    ],
    "success": true
}
```

### Error

The following error can occur upon the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **No Room Id**: Occurs when no `rid` is given.
* **Invalid Room**: Occurs when the given `rid` is invalid.

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
```javascript
{
    "success": false,
    "error": "Match error: Expected string, got undefined"
}
```
{% endtab %}

{% tab title="Invalid Room Id" %}
```javascript
{
    "success": false,
    "error": "Invalid room [error-invalid-room]",
    "errorType": "error-invalid-room",
    "details": {
        "method": "canAccessRoom"
    
```
{% endtab %}
{% endtabs %}
