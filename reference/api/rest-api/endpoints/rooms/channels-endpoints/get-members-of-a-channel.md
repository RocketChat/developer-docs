# Get Members of a Channel

Lists all channel users.

<table><thead><tr><th width="163">HTTP Method</th><th width="320">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/channels.members</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

This endpoint supports the [#pagination](../../../#pagination "mention") parameters. Additional query parameters are as follows:

{% hint style="info" %}
The list of elements a user can use to sort the list is limited. The current sortable element is:`username`
{% endhint %}

<table><thead><tr><th width="205">Key</th><th width="244">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark> or <code>roomName</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code> or <code>general</code></td><td>The channel ID or the channel name. You must enter at least one of these parameters.</td></tr><tr><td><code>status</code></td><td><code>['online', 'away']</code></td><td>The user's status (search filter).</td></tr><tr><td><code>filter</code></td><td><code>my-nickname</code></td><td>Extra search filters to be applied to the fields defined in the <code>Accounts_SearchFields</code> setting.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     https://localhost:3000/api/v1/channels.members?roomId=ByehQjC44FwMeiLbX&count=2
```

## Example Response

```json
{
    "members": [
        {
            "_id": "Loz7qh9ChSqHMPymx",
            "username": "customField_apiuser.test.1529436896005",
            "name": "customField_apiuser.test.1529436896005",
            "status": "offline"
        },
        {
            "_id": "Zc3Y3cRW7ZtS7Y8Hk",
            "username": "customField_apiuser.test.1529436997563",
            "name": "customField_apiuser.test.1529436997563",
            "status": "offline"
        }
    ],
    "count": 2,
    "offset": 0,
    "total": 35,
    "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.59.0  | Added       |
