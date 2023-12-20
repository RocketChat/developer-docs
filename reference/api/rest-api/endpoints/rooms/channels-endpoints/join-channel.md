# Join Channel

Join a channel yourself.

<table><thead><tr><th width="163">HTTP Method</th><th width="316">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/channels.join</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="220.33333333333331">Key</th><th width="234">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The channel ID that you want to join.</td></tr><tr><td><code>joinCode</code></td><td><code>1234</code></td><td>The join code of the room.</td></tr></tbody></table>

{% hint style="info" %}
The join code isn't needed if the user has the permission `join-without-join-code`.
{% endhint %}

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     https://localhost:3000/api/v1/channels.join \
     -d '{ 
          "roomId": "ByehQjC44FwMeiLbX", 
          "joinCode": "1234" }'
```

## Example Response

```json
{
    "channel": {
        "_id": "nxXKHF2o2nzKYtFMM",
        "name": "test",
        "fname": "test",
        "t": "c",
        "msgs": 8,
        "usersCount": 2,
        "u": {
            "_id": "rocketchat.internal.admin.test",
            "username": "rocketchat.internal.admin.test"
        },
        "customFields": {},
        "broadcast": false,
        "encrypted": false,
        "ts": "2019-01-16T12:00:04.783Z",
        "ro": false,
        "sysMes": true,
        "default": false,
        "_updatedAt": "2019-01-16T12:06:30.426Z",
        "joinCodeRequired": true
    },
    "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.49.0  | Added       |
