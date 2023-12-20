# Get Channel Information

Retrieves the information about the channel. This does not include archived channels.

<table><thead><tr><th width="163">HTTP Method</th><th width="316">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/channels.info</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

<table><thead><tr><th width="200.33333333333331">Key</th><th width="241">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark> or <code>roomName</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The channel ID or the name. You must enter at least one of the parameters.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     https://localhost:3000/api/v1/channels.info?roomId=ByehQjC44FwMeiLbX
```

## Example Response

```json
{
  "channel": {
    "_id": "ByehQjC44FwMeiLbX",
    "name": "testing",
    "fname": "testing",
    "t": "c",
    "msgs": 0,
    "usersCount": 2,
    "u": {
      "_id": "HKKPmF8rZh45GMHWH",
      "username": "marcos.defendi"
    },
    "customFields": {},
    "broadcast": false,
    "encrypted": false,
    "ts": "2020-05-21T13:14:07.070Z",
    "ro": false,
    "default": false,
    "sysMes": true,
    "_updatedAt": "2020-05-21T13:14:07.096Z"
  },
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.48.0  | Added       |
