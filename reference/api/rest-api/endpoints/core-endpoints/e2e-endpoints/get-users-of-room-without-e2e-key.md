---
description: Retrieves Users Of Room Without E2E Key
---

# Get Users Of Room Without E2E Key

| `URL`                                 | `Requires Auth` | `HTTP Method` |
| ------------------------------------- | --------------- | ------------- |
| `api/v1/e2e.getUsersOfRoomWithoutKey` | `YES`           | `GET`         |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Query Params

| Argument | Example             | Required | Description     |
| -------- | ------------------- | -------- | --------------- |
| `rid`    | `zRAeTszXor8CCPceB` | Required | The room `_id`. |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/e2e.getUsersOfRoomWithoutKey\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

### Success

```javascript
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
