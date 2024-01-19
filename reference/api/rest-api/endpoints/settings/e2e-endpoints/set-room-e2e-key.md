---
description: Sets the end-to-end encryption key ID for a room
---

# Set Room E2E Key

| URL                        | Requires Auth                            | HTTP Method |
| -------------------------- | ---------------------------------------- | ----------- |
| `/api/v1/e2e.setRoomKeyID` | [`Yes`](../../authentication-endpoints/) | `POST`      |

## Body Parameters

<table><thead><tr><th width="157">Argument</th><th>Example</th><th width="142">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>rid</code></td><td><code>Qe3Wa3outaDMKzAZC</code></td><td>Required</td><td>The Room Id</td></tr><tr><td><code>keyID</code></td><td><code>my-UniQu3_ke4_Id</code></td><td>Required</td><td>The key you wish to set.</td></tr></tbody></table>

## Example Call

```powershell
curl --location --request POST 'http://localhost:3000/api/v1/e2e.setRoomKeyID' \
--header 'X-User-Id: d26x6zSkaPSe5gCyy' \
--header 'X-Auth-Token: Di9OKWzdu7V2vW3lHO0oYLOOr6P2Y0n9zQlx20qn2cU' \
--header 'Content-Type: application/json' \
--data-raw '{
    "rid": "wCiXndNp5NqNY3uCc",
    "keyID": "my-UniQu3_ke4_Id"
}'
```

## Example Response

### Success

```json
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
