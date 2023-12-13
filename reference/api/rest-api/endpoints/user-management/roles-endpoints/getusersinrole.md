# Get Users of a Role

Gets the users that belong to a specific role.

<table><thead><tr><th width="163">HTTP Method</th><th width="319">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/roles.getUsersInRole</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

This endpoint supports the optional offset and count [#pagination](../../../#pagination "mention") query parameters.

<table><thead><tr><th width="205">Key</th><th width="243">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>role</code><mark style="color:red;"><code>*</code></mark></td><td><code>admin</code></td><td>The role.</td></tr><tr><td><code>roomId</code></td><td><code>GENERAL</code></td><td>The room ID.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/roles.getUsersInRole
```

## Example Response

```json
{
  "users": [
    {
      "_id": "voakrL3cHjYBwwRPq",
      "username": "a",
      "type": "user",
      "status": "offline",
      "active": true,
      "name": "a"
    },
    {
      "_id": "N2s7KG6YkzgJfXbyn",
      "username": "b",
      "type": "user",
      "status": "offline",
      "active": true,
      "name": "b"
    },
  ],
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 1.3.0   | Added       |
