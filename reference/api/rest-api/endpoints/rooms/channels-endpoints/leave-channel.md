# Leave Channel

<table><thead><tr><th width="163">HTTP Method</th><th width="316">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/channels.leave</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="219.33333333333331">Key</th><th width="236">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The channel ID that you want to leave.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     https://localhost:3000/api/v1/channels.leave \
     -d '{ 
          "roomId": "ByehQjC44FwMeiLbX" }'
```

## Example Response

```json
{
  "channel": {
    "_id": "ByehQjC44FwMeiLbX",
    "name": "invite-me",
    "t": "c",
    "usernames": [
      "testing2"
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
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.48.0  | Added       |
