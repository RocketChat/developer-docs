# Invite to Channel

Adds a user or bulk users to the channel.

<table><thead><tr><th width="163">HTTP Method</th><th width="316">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/channels.invite</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
For a user to invite others, they must match at least one of the following premises:

* If the user is part of a room of any type and has the `add-user-to-joined-room` permission.
* If the user is part of a public room (`t: 'c'`) and has the `add-user-to-any-c-room` permission.
* If the user is part of a private room (`t: 'p'`) and has the `add-user-to-any-p-room` permission.
{% endhint %}

## Add a user

### Body Parameters

<table><thead><tr><th width="206.33333333333331">Key</th><th width="255">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The channel ID.</td></tr><tr><td><code>userId</code><mark style="color:red;"><code>*</code></mark></td><td><code>nSYqWzZ4GsKTX4dyK</code></td><td>The user ID to invite to the channel.</td></tr></tbody></table>

### Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     https://localhost:3000/api/v1/channels.invite \
     -d '{ 
          "roomId": "ByehQjC44FwMeiLbX", 
          "userId": "nSYqWzZ4GsKTX4dyK" }'
```

### Example Response

```json
{
  "channel": {
    "_id": "ByehQjC44FwMeiLbX",
    "ts": "2016-11-30T21:23:04.737Z",
    "t": "c",
    "name": "testing",
    "usernames": "testing",
    "msgs": 1,
    "_updatedAt": "2016-12-09T12:50:51.575Z",
    "lm": "2016-12-09T12:50:51.555Z"
  },
  "success": true
}
```

## Add bulk users

### Body Parameters

<table><thead><tr><th width="212.33333333333331">Key</th><th>Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The channel ID.</td></tr><tr><td><code>userIds</code><mark style="color:red;"><code>*</code></mark></td><td><code>["nSYqWzZ4GsKTX4dyK", "SYqWzZ4Gsasdfgh"]</code></td><td>The user IDs of the users to invite to the channel</td></tr></tbody></table>

### Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/channels.invite \
     -d '{ 
          "roomId": "ByehQjC44FwMeiLbX", 
          "userIds": ["nSYqWzZ4GsKTX4dyK", "SYqWzZ4Gsasdfgh"]}'
```

### Example Response

```json
{
  "channel": {
    "_id": "ByehQjC44FwMeiLbX",
    "ts": "2016-11-30T21:23:04.737Z",
    "t": "c",
    "name": "testing",
    "usernames": [
      "testing",
      "testing1"
    ],
    "msgs": 1,
    "_updatedAt": "2016-12-09T12:50:51.575Z",
    "lm": "2016-12-09T12:50:51.555Z"
  },
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.48.0  | Added       |
