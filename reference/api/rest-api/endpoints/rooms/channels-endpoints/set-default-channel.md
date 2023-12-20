# Set Default Channel

Sets whether the channel is a default channel or not.

<table><thead><tr><th width="163">HTTP Method</th><th width="320">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/channels.setDefault</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="202.33333333333331">Key</th><th width="224">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The channel ID.</td></tr><tr><td><code>default</code><mark style="color:red;"><code>*</code></mark></td><td><code>true</code></td><td>Boolean of whether the room is default or not.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     https://localhost:3000/api/v1/channels.setDefault \
     -d '{ 
          "roomId": "ByehQjC44FwMeiLbX", 
          "default": true }'
```

## Example Response

```json
{
    "channel": {
        "_id": "ByehQjC44FwMeiLbX",
        "name": "testing0",
        "t": "c",
        "msgs": 0,
        "u": {
            "_id": "aiPqNoGkjpNDiRx6d",
            "username": "goose160"
        },
        "ts": "2017-01-05T18:02:50.754Z",
        "ro": true,
        "sysMes": true,
        "_updatedAt": "2017-01-05T19:02:24.429Z",
        "usernames": [
            "goose160",
            "graywolf336"
        ],
        "joinCodeRequired": true,
        "muted": [],
        "default": true
    },
    "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.66.0  | Added       |
