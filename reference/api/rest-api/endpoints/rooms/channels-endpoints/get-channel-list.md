# Get Channel List

<table><thead><tr><th width="163">HTTP Method</th><th width="347">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/channels.list</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

This endpoint supports the optional [#pagination](../../../#pagination "mention") parameters, alongside the [#query-and-fields](../../../#query-and-fields "mention") parameters.

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     https://localhost:3000/api/v1/channels.list
```

## Example Response

```json
{
    "channels": [
        {
            "_id": "ByehQjC44FwMeiLbX",
            "name": "test-test",
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
        },
        {
            "_id": "t7qapfhZjANMRAi5w",
            "name": "testing",
            "t": "c",
            "usernames": [
                "testing2"
            ],
            "msgs": 0,
            "u": {
                "_id": "y65tAmHs93aDChMWu",
                "username": "testing2"
            },
            "ts": "2016-12-01T15:08:58.042Z",
            "ro": false,
            "sysMes": true,
            "_updatedAt": "2016-12-09T15:22:40.656Z"
        }
    ],
    "offset": 0,
    "count": 1,
    "total": 1,
    "success": true
}
```

## Change Log

| Version | Description                                  |
| ------- | -------------------------------------------- |
| 0.49.0  | Count and offset query parameters supported. |
| 0.48.0  | Added                                        |
