# Get Users List

Gets all of the users in the system and their information, the result is only limited to what the request sender has access to view.

<table><thead><tr><th width="163">HTTP Method</th><th width="311">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/users.list</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

This endpoint supports the optional [#pagination](../../../#pagination "mention") parameters and the [#query-and-fields](../../../#query-and-fields "mention") parameters.

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/users.list
```

## Example Response&#x20;

If the request sender is a regular user:

```json
{
  "users": [
    {
      "_id": "nSYqWzZ4GsKTX4dyK",
      "type": "user",
      "status": "offline",
      "active": true,
      "name": "Example User",
      "utcOffset": 0,
      "username": "example"
    },
    {
      ...
    }
  ],
  "count": 10,
  "offset": 0,
  "total": 10,
  "success": true
}
```

If the request sender is an admin:

```javascript
{
    "users": [
        {
            "_id": "Bm9YcfBCrwSTSGof7",
            "username": "botkit.user",
            "emails": [
                {
                    "address": "botkit@user.cm",
                    "verified": false
                }
            ],
            "status": "offline",
            "active": true,
            "roles": [
                "bot"
            ],
            "name": "Botkit User",
            "nameInsensitive": "botkit user"
        },
        
        {
            "_id": "Fdh2KgsB7dtwbYrNw",
            "username": "john.m",
            "emails": [
                {
                    "address": "john@m.com",
                    "verified": true
                }
            ],
            "status": "offline",
            "active": true,
            "roles": [
                "user"
            ],
            "name": "John M",
            "nameInsensitive": "john m"
        },
        {...},
        {
            "_id": "jowYXPgJoKaoxzz4q",
            "username": "user.one",
            "emails": [
                {
                    "address": "remego8086@d3ff.com",
                    "verified": false
                }
            ],
            "status": "offline",
            "active": true,
            "roles": [
                "livechat-manager",
                "livechat-agent"
            ],
            "name": "User One",
            "nameInsensitive": "user one"
        }
    ],
    "count": 11,
    "offset": 0,
    "total": 11,
    "success": true
}
```

Note that the response does not return the custom fields for users. To view the custom field information, you must add the `query` and `fields` [parameters](https://developer.rocket.chat/reference/api/rest-api#query-and-fields).&#x20;

For example, you want to view the users having the custom field `clearance` with the value `High`. To do this, update the request URL as follows:

* Add the `query` parameter: `query={"customFields.clearance" : "High"}`
* Add the `fields` parameter: `fields={"customFields" : 1}`

{% code overflow="wrap" %}
```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/users.list?query={"customFields.clearance" : "High"}&fields={"customFields" : 1}
```
{% endcode %}

{% hint style="info" %}
To save and view the custom fields, you must first define the **Custom Fields** in the admin panel of your workspace (**Administration** > **Settings** > **Accounts** > **Registration** > [**Custom Fields**](https://docs.rocket.chat/use-rocket.chat/workspace-administration/settings/accounts/custom-fields)).
{% endhint %}

## Change Log

<table><thead><tr><th width="329">Version</th><th>Description</th></tr></thead><tbody><tr><td>0.49.0</td><td>Count and offset query parameters supported.</td></tr><tr><td>0.35.0</td><td>Added</td></tr></tbody></table>
