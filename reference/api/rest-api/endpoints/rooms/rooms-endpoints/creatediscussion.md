# Create Discussion

Creates a new discussion for the room. It requires at least one of the following permissions: `start-discussion` OR `start-discussion-other-user`, AND must be with the following setting enabled: `Discussion_enabled`.

<table><thead><tr><th width="163">HTTP Method</th><th width="298">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/rooms.createDiscussion</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="184.33333333333331">Key</th><th width="237">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>prid</code><mark style="color:red;"><code>*</code></mark></td><td><code>GENERAL</code></td><td>Parent room ID of the discussion.</td></tr><tr><td><code>t_name</code><mark style="color:red;"><code>*</code></mark></td><td><code>discussion name</code></td><td>Discussion name.</td></tr><tr><td><code>users</code></td><td><code>['rocket.cat']</code></td><td>Array of users to join in the discussion, if not provided, it will be an empty array. (Note: if provided, it must be an array).</td></tr><tr><td><code>pmid</code></td><td><code>aobEgbghXfe543keqG</code></td><td>Parent message ID (if the discussion comes from a message).</td></tr><tr><td><code>reply</code></td><td><code>reply of this discussion</code></td><td>The reply of the discussion.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-Type: application/json" \
     http://localhost:3000/api/v1/rooms.createDiscussion  \
     -d '{ 
          "prid": "GENERAL", 
          "t_name": "Discussion Name"}'
```

## Example Response

```json
{
    "discussion": {
        "rid": "cgk88DHLHexwMaFWh",
        "name": "WJNEAM7W45wRYitHo",
        "fname": "Discussion Name",
        "t": "p",
        "msgs": 0,
        "usersCount": 0,
        "u": {
            "_id": "rocketchat.internal.admin.test",
            "username": "rocketchat.internal.admin.test"
        },
        "topic": "general",
        "prid": "GENERAL",
        "ts": "2019-04-03T01:35:32.271Z",
        "ro": false,
        "sysMes": true,
        "default": false,
        "_updatedAt": "2019-04-03T01:35:32.280Z",
        "_id": "cgk88DHLHexwMaFWh"
    },
    "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 1.0.0   | Added       |
