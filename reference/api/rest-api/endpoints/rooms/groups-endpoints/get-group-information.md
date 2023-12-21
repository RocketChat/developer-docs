# Get Group Information

Retrieves the information about the group/channel, only if you're part of the group.

<table><thead><tr><th width="163">HTTP Method</th><th width="313">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/groups.info</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

Only one of the `roomId` or `roomName` parameters are required.

<table><thead><tr><th width="176">Key</th><th width="244">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The group ID.</td></tr><tr><td><code>roomName</code><mark style="color:red;"><code>*</code></mark></td><td><code>Exclusive.Chat</code></td><td>The group name.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/groups.info?roomId=ByehQjC44FwMeiLbX
```

## Example Response

```json
{
  "group": {
    "_id": "ByehQjC44FwMeiLbX",
    "name": "testing",
    "fname": "testing",
    "t": "p",
    "msgs": 0,
    "usersCount": 2,
    "u": {
      "_id": "HKKPmF8rZh45GMHWH",
      "username": "marcos.defendi"
    },
    "customFields": {},
    "broadcast": false,
    "encrypted": false,
    "ts": "2020-05-21T13:16:24.749Z",
    "ro": false,
    "default": false,
    "sysMes": true,
    "_updatedAt": "2020-05-21T13:16:24.772Z"
  },
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.48.0  | Added       |
