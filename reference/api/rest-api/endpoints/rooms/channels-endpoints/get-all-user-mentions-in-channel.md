# Get All User Mentions in Channel

<table><thead><tr><th width="163">HTTP Method</th><th width="320">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/channels.getAllUserMentionsByChannel</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

This endpoint supports the [#pagination](../../../#pagination "mention") parameters.

<table><thead><tr><th width="197.33333333333331">Key</th><th width="226">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The channel ID.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     https://localhost:3000/api/v1/channels.getAllUserMentionsByChannel?roomId=ByehQjC44FwMeiLbX
```
{% endcode %}

## Example Response

```json
{
    "mentions": [
        {
            "_id": "Gptx3mc6TjSv5tLWb",
            "rid": "GENERAL",
            "msg": "@rocket.cat",
            "ts": "2018-03-12T14:59:14.166Z",
            "u": {
                "_id": "47cRd58HnWwpqxhaZ",
                "username": "test",
                "name": "test"
            },
            "mentions": [
                {
                    "_id": "47cRd58HnWwpqxhaZ",
                    "username": "rocket.cat"
                }
            ],
            "channels": [],
            "_updatedAt": "2018-03-12T14:59:14.171Z"
        },
        {
            "_id": "rwerwfjuii6TjSv5tLWb",
            "rid": "GENERAL",
            "msg": "@rocket.cat",
            "ts": "2018-03-12T14:59:14.166Z",
            "u": {
                "_id": "47cRd58HnWwpqxhaZ",
                "username": "test",
                "name": "test"
            },
            "mentions": [
                {
                    "_id": "47cRd58HnWwpqxhaZ",
                    "username": "rocket.cat"
                }
            ],
            "channels": [],
            "_updatedAt": "2018-03-12T14:59:14.171Z"
        }
    ],
    "count": 2,
    "offset": 10,
    "total": 2,
    "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.63.0  | Added       |
