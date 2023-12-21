# Get Room Information

Retrieves the information about a specific room. &#x20;

<table><thead><tr><th width="163">HTTP Method</th><th width="298">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/rooms.info</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

This endpoint supports only the `field` parameter for[#query-and-fields](../../../#query-and-fields "mention"). Additional parameters are as follows:

<table><thead><tr><th width="227.33333333333331">Key</th><th>Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark> or <code>roomName</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code> or <code>general</code></td><td>The room ID or name. You must enter at least one of the parameters.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/rooms.info?roomId=ByehQjC44FwMeiLbX
```

## Example Response

```json
{
  "room": {
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
| 0.72.0  | Added       |
