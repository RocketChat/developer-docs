# Get Users Presence

<table><thead><tr><th width="166">HTTP Method</th><th width="347">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/users.presence</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
If the **Presence\_broadcast\_disabled** setting is true, the endpoint returns an empty array.
{% endhint %}

## Query Parameters

<table><thead><tr><th width="158">Key</th><th width="278">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>from</code></td><td><code>2019-05-22T12:11:45.392Z</code></td><td>The last date when the status was changed.<br>Format: ISO 8601 datetime. Timezone, milliseconds and seconds are optional</td></tr><tr><td><code>ids</code></td><td><code>J4sWseCgs8eEnWvhE</code></td><td>The user IDs whose status you want.</td></tr></tbody></table>

## Example Call - Without Parameters

If you don't pass `from` parameter, you'll get a list of all users' presence and the result will have a `full` field with value `true` .

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/users.presence
```

### Example Response

```json
{
   "users":[
      {
         "_id":"rocket.cat",
         "name":"Rocket.Cat",
         "username":"rocket.cat",
         "status":"online",
         "utcOffset":0,
         "avatarETag": "5BB9B5ny5DkKdrwkq"
      },
      {
         "_id":"rocketchat.internal.admin.test",
         "name":"RocketChat Internal Admin Test",
         "username":"rocketchat.internal.admin.test",
         "status":"online",
         "utcOffset":-2,
         "avatarETag": "iEbEm4bTT327NJjXt"
      }
   ],
   "full": true,
   "success":true
}
```

## Example Call - With `from` Parameter

If you pass the `from` parameter, you'll get only a list of users' presence that has changed after the time of `from` parameter. The `full` result field will then be `false`, indicating it's a partial result.

If the value of `from` parameter is older than 10 minutes, the server will reply with a **full** result set.

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/users.presence?from=2019-05-22T12:11:45.392Z
```

### Example Response

```json
{
   "users":[
      {
         "_id":"rocket.cat",
         "name":"Rocket.Cat",
         "username":"rocket.cat",
         "status":"online",
         "utcOffset":0,
         "avatarETag": "5BB9B5ny5DkKdrwkq"
      },
      {
         "_id":"rocketchat.internal.admin.test",
         "name":"RocketChat Internal Admin Test",
         "username":"rocketchat.internal.admin.test",
         "status":"online",
         "utcOffset":-2,
         "avatarETag": "iEbEm4bTT327NJjXt"
      }
   ],
   "full": false,
   "success":true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 1.1.0   | Added       |
