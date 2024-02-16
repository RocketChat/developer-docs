# Get Admin of Room

Retrieves the admin of a room (requires the `view-room-administration` permission).

<table><thead><tr><th width="163">HTTP Method</th><th width="298">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/rooms.adminRooms.getRoom</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

<table><thead><tr><th width="163">Key</th><th width="298">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>rid</code><mark style="color:red;"><code>*</code></mark></td><td><code>654c9d1ca2f73c7460e1918b</code></td><td>The room ID.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```bash
curl -L -X GET 'http://localhost:3000/api/v1/rooms.adminRooms.getRoom?rid=654c9d1ca2f73c7460e1918b' \
-H 'X-User-Id: d26x6zSkaPSe5gCyy' \
-H 'X-Auth-Token: Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92'
```
{% endcode %}

## Example Response

### Success

```json
{
    "_id": "ukFsHiySDhMkQyyyF",
    "name": "freightwave",
    "fname": "freightwave",
    "t": "p",
    "msgs": 4,
    "usersCount": 1,
    "u": {
        "_id": "Gd6iymRZBK4C6wqHN",
        "username": "bruno.raymundo"
    },
    "ro": false,
    "default": false,
    "success": true
}
```

### Error

Any of the following errors can occur:

* **Authorization**: Requires an authentication token for the request to be made.
* **No Permission**: Occurs when the authenticated user doesn't have the `view-room-administration` permission.
* **Missing query parameter:** Occurs when the required parameter `rid` is missing.

{% tabs %}
{% tab title=" Authorization" %}
```json
{
    "success": false,
    "error": "unauthorized"
}
```
{% endtab %}

{% tab title="No Permission" %}
```json
{
    "success": false,
    "error": "error-not-authorized"
}
```
{% endtab %}

{% tab title="Missing Query Parameter" %}
```json
{
    "success": false,
    "error": "not-allowed",
    "errorType": "Not Allowed"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 2.4.0   | Added       |
