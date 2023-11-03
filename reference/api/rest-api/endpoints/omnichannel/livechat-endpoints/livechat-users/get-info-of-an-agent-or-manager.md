# Get Agent or Manager Information

Get information about a particular agent or a manager.

<table><thead><tr><th width="163">HTTP Method</th><th width="250">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/users/:type/:_id</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Path Variables

<table><thead><tr><th width="155.00000000000003">Key</th><th width="208">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>type </code><mark style="color:red;"><code>*</code></mark></td><td><code>agent</code></td><td>The type of user. The value can either be <code>agent</code> or <code>manager</code>.</td></tr><tr><td><code>_id </code><mark style="color:red;"><code>*</code></mark></td><td><code>SQafHvoFPuB57NmBD</code></td><td>The user <code>_id</code>.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location 'http://localhost:3000/api/v1/livechat/users/agent/PSaBmpB2c9eFaE79q' \
--header 'X-Auth-Token: Y97tM4GkYjgaH_fIO5dwBitQQvm3yp-AptYzGQZMX6e' \
--header 'X-User-Id: CkCPNcvsvCDfmWLqC' \
--data ''
```
{% endcode %}

## Example Response

```json
{
  "user": {
    "_id": "SQafHvoFPuB57NmBD",
    "username": "john.doe",
    "name": "John Doe",
    "status": "offline",
    "statusLivechat": "available",
    "emails": [
    {
        "address": "john.doe@test.com",
        "verified": "true"
    }
    ],
    "livechat": {
        "maxNumberSimultaneousChat": ""
    }
  },
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.42.0  | Added       |
