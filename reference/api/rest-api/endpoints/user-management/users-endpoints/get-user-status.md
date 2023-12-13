# Get User Status

<table><thead><tr><th width="163">HTTP Method</th><th width="279">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/users.getStatus</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

<table><thead><tr><th width="228.33333333333331">Key</th><th width="229">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>userId</code> or <code>username</code></td><td><code>BsNr28znDkG8aeo7W</code> or <code>bobsmith</code></td><td>The ID or username of the user. If not provided, the status of the user who is sending the request is returned.</td></tr></tbody></table>

## Example Call

With the `userId` query parameter:

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/users.getStatus?userId=BsNr28znDkG8aeo7W
```

With no query parameter:

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/users.getStatus
```

## Example Response

```json
{
    "message": "Latest status",
    "connectionStatus": "online",
    "status": "online",
    "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 1.2.0   | Added       |
