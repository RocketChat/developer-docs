# Rename Group

Changes the name of the group/channel.

<table><thead><tr><th width="180">HTTP Method</th><th width="313">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/groups.rename</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="197.33333333333331">Key</th><th width="235">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The group ID.</td></tr><tr><td><code>name</code><mark style="color:red;"><code>*</code></mark></td><td><code>new-name</code></td><td>The new name of the group. It can not be the same as another group or the existing name.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/groups.rename \
     -d '{ 
          "roomId": "ByehQjC44FwMeiLbX", 
          "name": "new-name" }'
```

## Example Response

```json
{
  "group": {
    "_id": "ByehQjC44FwMeiLbX",
    "name": "new-name",
    "t": "p",
    "usernames": [
      "testing1"
    ],
    "msgs": 4,
    "u": {
      "_id": "aobEdbYhXfu5hkeqG",
      "username": "testing1"
    },
    "ts": "2016-12-09T15:08:58.042Z",
    "ro": false,
    "sysMes": true,
    "_updatedAt": "2016-12-09T15:57:44.686Z"
  },
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.48.0  | Added       |
