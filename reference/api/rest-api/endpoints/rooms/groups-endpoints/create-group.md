# Create Group

Creates a new group/channel, optionally including specified users. The group creator is always included.

<table><thead><tr><th width="163">HTTP Method</th><th width="313">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/groups.create</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="205.33333333333331">Key</th><th width="196">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>name</code><mark style="color:red;"><code>*</code></mark></td><td><code>testing</code></td><td>The name of the new private group.</td></tr><tr><td><code>members</code></td><td><code>["rocket.cat"]</code></td><td>The users to be added to the group when it is created.</td></tr><tr><td><code>readOnly</code></td><td><code>true</code></td><td>Set if the group is read only or not. The default value is <code>false</code>.</td></tr><tr><td><code>excludeSelf</code></td><td><code>true</code></td><td>If set to <code>true</code> the user calling the endpoint is not automatically added as a member of the group. The default value is <code>false</code>.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/groups.create \
     -d '{ 
          "name": "testing" }'
```

## Example Response

```json
{
  "group": {
    "_id": "NtR6RQ7NvzA9ejecX",
    "name": "testing",
    "t": "p",
    "msgs": 0,
    "u": {
      "_id": "aobEdbYhXfu5hkeqG",
      "username": "tester"
    },
    "ts": "2016-12-09T16:53:06.761Z",
    "ro": false,
    "sysMes": true,
    "_updatedAt": "2016-12-09T16:53:06.761Z"
  },
  "success": true
}
```

## Change Log

| Version | Description               |
| ------- | ------------------------- |
| 6.4.1   | Added `excludeSelf` param |
| 0.35.0  | Added                     |
