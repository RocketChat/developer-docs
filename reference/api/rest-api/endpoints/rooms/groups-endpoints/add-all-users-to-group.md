# Add All Users to Group

Adds all of the users of the Rocket.Chat workspace to the group/channel.

<table><thead><tr><th width="163">HTTP Method</th><th width="313">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/groups.addAll</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="224.33333333333331">Key</th><th width="229">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The channel ID.</td></tr><tr><td><code>activeUsersOnly</code></td><td><code>true</code></td><td>Add active users only. By default, the value is <code>false</code>.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/channels.addAll \
     -d '{ 
          "roomId": "ByehQjC44FwMeiLbX" }'
```

## Example Response

```json
{
   "channel": {
      "_id": "ByehQjC44FwMeiLbX",
      "name": "groupname",
      "t": "p",
      "usernames": [
         "example",
         "rocket.cat"
      ],
      "msgs": 0,
      "u": {
         "_id": "aobEdbYhXfu5hkeqG",
         "username": "example"
      },
      "ts": "2016-05-30T13:42:25.304Z"
   },
   "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.55.0  | Added       |
