# Get Livechat Trigger

Get the details about a specific trigger.

<table><thead><tr><th width="163">HTTP Method</th><th width="332">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/triggers/:_id</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `view-livechat-manager`
{% endhint %}

## Path Variables

<table><thead><tr><th width="163">Key</th><th width="285">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>_id</code><mark style="color:red;"><code>*</code></mark></td><td><code>Lk52shJFYyb55trw8</code></td><td>The trigger ID.</td></tr></tbody></table>

## Example Call

```powershell
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/livechat/triggers/Lk52shJFYyb55trw8
```

## Example Response

```json
{
    "trigger": {
        "_id": "Lk52shJFYyb55trw8",
        "name": "test",
        "description": "test",
        "enabled": true,
        "runOnce": true,
        "conditions": [
            {
                "name": "page-url",
                "value": ""
            }
        ],
        "actions": [
            {
                "name": "send-message",
                "params": {
                    "sender": "",
                    "msg": ""
                }
            }
        ],
        "_updatedAt": "2019-10-04T15:36:29.695Z"
    },
    "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 2.2.0   | Added       |
