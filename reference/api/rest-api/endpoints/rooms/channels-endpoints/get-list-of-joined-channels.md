# Get List of Joined Channels

Lists all of the channels the calling user has joined.

<table><thead><tr><th width="163">HTTP Method</th><th width="347">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/channels.list.joined</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

This endpoint supports the optional [#pagination](../../../#pagination "mention") parameters, alongside the `field` parameter for [#query-and-fields](../../../#query-and-fields "mention").

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     https://localhost:3000/api/v1/channels.list.joined
```

## Example Response

```json
{
    "channels": [
        {
            "_id": "ByehQjC44FwMeiLbX",
            "name": "invite-me",
            "t": "c",
            "usernames": [
                "testing1"
            ],
            "msgs": 0,
            "u": {
                "_id": "aobEdbYhXfu5hkeqG",
                "username": "testing1"
            },
            "ts": "2016-12-09T15:08:58.042Z",
            "ro": false,
            "sysMes": true,
            "_updatedAt": "2016-12-09T15:22:40.656Z"
        }
    ],
    "success": true
}
```

## Change Log

| Version | Description                                  |
| ------- | -------------------------------------------- |
| 0.62.0  | Add 'query' parameter support.               |
| 0.49.0  | Count and offset query parameters supported. |
| 0.48.0  | Added                                        |
