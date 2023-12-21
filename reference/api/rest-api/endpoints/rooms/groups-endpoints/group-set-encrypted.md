# Set Group as Encrypted

<table><thead><tr><th width="176">HTTP Method</th><th width="313">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/groups.setEncrypted</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="227">Key</th><th width="215.33333333333331">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>encrypted</code><mark style="color:red;"><code>*</code></mark></td><td><code>true</code></td><td>Whether or not to encrypt the room.</td></tr><tr><td><code>roomID</code><mark style="color:red;"><code>*</code></mark> or <code>roomName</code><mark style="color:red;"><code>*</code></mark></td><td><code>JZ8Y2dLfYhsg323Rf</code> or <code>My Group</code></td><td>The group ID or name on which to set the encryption.</td></tr></tbody></table>

## Example Call

```bash
curl -L -X POST 'http://localhost:3000/api/v1/groups.setEncrypted' \
-H 'X-User-Id: d26x6zSkaPSe5gCyy' \
-H 'X-Auth-Token: Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92' \
-H 'Content-Type: application/json' \
--data-raw '{
    "encrypted": false,
    "roomId": "JZ8Y2dLfYhsg323Rf"
}'
```

## Example Response

### Success

```json
{
    "group": {
        "_id": "JZ8Y2dLfYhsg323Rf",
        "fname": "test",
        "description": "",
        "broadcast": false,
        "encrypted": false,
        "teamMain": true,
        "name": "test",
        "t": "p",
        "msgs": 0,
        "usersCount": 1,
        "u": {
            "_id": "d26x6zSkaPSe5gCyy",
            "username": "rodriq"
        },
        "ts": "2021-10-22T11:59:17.029Z",
        "ro": false,
        "teamId": "6172a795c563fc000acc4629",
        "_updatedAt": "2021-10-22T12:00:11.496Z"
    },
    "success": true
}
```

### Error

Any of the following errors can occur:

* **Authorization**: Requires an authentication token for the request to be made.
* **No encrypted parameter**: Occurs when the endpoint is called without the encrypted body param.
* **No Room Id or roomName**: Occurs when no `roomID` or `roomName` is given.
* **Invalid Room**: Occurs when the given room is invalid.

{% tabs %}
{% tab title=" Authorization" %}
```javascript
{
    "success": false,
    "error": "unauthorized"
}
```
{% endtab %}

{% tab title="No Room Id or Name" %}
```
{
    "success": false,
    "error": "The parameter \"roomId\" or \"roomName\" is required [error-room-param-not-provided]",
    "errorType": "error-room-param-not-provided"
}
```
{% endtab %}

{% tab title="Invalid Room ID" %}
```
{
    "success": false,
    "error": "The required \"roomId\" or \"roomName\" param provided does not match any group [error-room-not-found]",
    "errorType": "error-room-not-found"
}
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 3.13.0  | Added       |
