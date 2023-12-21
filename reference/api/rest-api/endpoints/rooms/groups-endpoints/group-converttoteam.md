# Convert Group to Team

<table><thead><tr><th width="176">HTTP Method</th><th width="313">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/groups.convertToTeam</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="180.33333333333331">Key</th><th width="265">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomID</code><mark style="color:red;"><code>*</code></mark> or <code>roomName</code><mark style="color:red;"><code>*</code></mark></td><td><code>JZ8Y2dLfYhsg323Rf</code> or <code>My Group</code></td><td>The name or ID of the group to convert to a team.</td></tr></tbody></table>

## Example Call

```bash
curl -L -X POST 'http://localhost:3000/api/v1/groups.convertToTeam' \
-H 'X-User-Id: d26x6zSkaPSe5gCyy' \
-H 'X-Auth-Token: Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92' \
-H 'Content-Type: application/json' \
--data-raw '{
    "roomId": "h3HLZkQdrWCPg2RN7"
}'
```

## Example Response

### Success

```json
{
    "team": {
        "_id": "6172b15bc563fc000acc462e",
        "name": "ddd",
        "type": 1,
        "createdAt": "2021-10-22T12:40:59.928Z",
        "createdBy": {
            "_id": "d26x6zSkaPSe5gCyy",
            "username": "rodriq"
        },
        "_updatedAt": "2021-10-22T12:40:59.928Z",
        "roomId": "h3HLZkQdrWCPg2RN7"
    },
    "success": true
}
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **Already Exists**: Senn when the team already exists.
* **No Room Id or roomName**: Occurs when no `roomID or roomName` is given.
* **Invalid Room**: Occurs when the given `room` is invalid.

{% tabs %}
{% tab title=" Authorization" %}
```json
{
    "success": false,
    "error": "unauthorized"
}
```
{% endtab %}

{% tab title="Already Exists" %}
```
{
    "success": false,
    "error": "team-name-already-exists"
}
```
{% endtab %}

{% tab title="No roomID or roomName" %}
```
{
    "success": false,
    "error": "The parameter \"roomId\" or \"roomName\" is required"
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
