# Invite Users to Group

Invite one user or bulk users to the group/channel.

<table><thead><tr><th width="163">HTTP Method</th><th width="313">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/groups.invite</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Invite a user

### Body Parameters

<table><thead><tr><th width="194.33333333333331">Key</th><th width="223">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The group ID.</td></tr><tr><td><code>userId</code><mark style="color:red;"><code>*</code></mark></td><td><code>nSYqWzZ4GsKTX4dyK</code></td><td>The user ID of the invited user.</td></tr></tbody></table>

### Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/groups.invite \
     -d '{ 
          "roomId": "ByehQjC44FwMeiLbX", 
          "userId": "nSYqWzZ4GsKTX4dyK" }'
```

### Example Response

```json
{
  "group": {
    "_id": "ByehQjC44FwMeiLbX",
    "ts": "2016-11-30T21:23:04.737Z",
    "t": "p",
    "name": "testing",
    "username": "testing",
    "u": {
        "_id": "aobEdbYhXfu5hkeqG",
        "username": "testing1"
    },
    "msgs": 1,
    "_updatedAt": "2016-12-09T12:50:51.575Z",
    "lm": "2016-12-09T12:50:51.555Z"
  },
  "success": true
}
```

## Invite bulk users

### Body Parameters

<table><thead><tr><th width="189.33333333333331">Key</th><th width="257">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The group ID.</td></tr><tr><td><code>userIds</code><mark style="color:red;"><code>*</code></mark></td><td><code>["nSYqWzZ4GsKTX4dyK", "SYqWzZ4Gsasdfgh"]</code></td><td>The user IDs of the invited users.</td></tr></tbody></table>

### Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/groups.invite \
     -d '{ 
          "roomId": "ByehQjC44FwMeiLbX", 
          "userIds": ["nSYqWzZ4GsKTX4dyK", "SYqWzZ4Gsasdfgh"] }'
```

### Example Response

```json
{
  "group": {
    "_id": "ByehQjC44FwMeiLbX",
    "ts": "2016-11-30T21:23:04.737Z",
    "t": "p",
    "name": "testing",
    "usernames": [
      "testing",
      "testing1"
    ],
    "u": {
        "_id": "aobEdbYhXfu5hkeqG",
        "username": "testing1"
    },
    "msgs": 1,
    "_updatedAt": "2016-12-09T12:50:51.575Z",
    "lm": "2016-12-09T12:50:51.555Z"
  },
  "success": true
}
```

## Error

If you are an administrator and try to invite a user to a group, of which you are not a member, then you will get an error:

```json
{
  "success": false,
  "error": "Not allowed [error-not-allowed]",
  "errorType": "error-not-allowed",
  "details": {
    "method": "addUsersToRoom"
  }
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.48.0  | Added       |
