# Set Channel Type

Set a channel as public or private.

<table><thead><tr><th width="163">HTTP Method</th><th width="320">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/channels.setType</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="193">Key</th><th width="214.33333333333331">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark> or <code>roomName</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code> or <code>chat-room-name</code></td><td>The channel ID or name. You must enter at least one of the parameters.</td></tr><tr><td><code>type</code><mark style="color:red;"><code>*</code></mark></td><td><code>c</code> <em>or</em> <code>p</code></td><td><p>The type of room this channel should be, either <code>c</code> or <code>p</code>. </p><p><code>c</code> is for channel and <code>p</code> is for private.</p></td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     https://localhost:3000/api/v1/channels.setType \
     -d '{ 
          "roomId": "ByehQjC44FwMeiLbX", 
          "type": "p" }'

or

curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     https://localhost:3000/api/v1/channels.setType \
     -d '{      
          "roomName": "chat-room-name", 
          "type": "p" }'
```

## Example Response

```json
{
    "channel": {
        "_id": "ByehQjC44FwMeiLbX",
        "name": "testing0",
        "t": "p",
        "msgs": 0,
        "u": {
            "_id": "aiPqNoGkjpNDiRx6d",
            "username": "goose160"
        },
        "ts": "2017-01-05T18:02:50.754Z",
        "ro": false,
        "sysMes": true,
        "_updatedAt": "2017-01-05T19:02:24.429Z",
        "usernames": [
            "goose160",
            "graywolf336"
        ],
        "joinCodeRequired": true,
        "muted": []
    },
    "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.49.0  | Added       |
