# Get Department Information

Get information about a specific department using the department ID.

<table><thead><tr><th width="163">HTTP Method</th><th width="305">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/department/:_id</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `view-l-room`
{% endhint %}

## Path Variables

<table><thead><tr><th width="205.33333333333331">Key</th><th width="240">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>_id</code><mark style="color:red;"><code>*</code></mark></td><td><code>SQafHvoFPuB57NmBD</code></td><td>The department <code>_id</code>.</td></tr></tbody></table>

## Query Parameters

<table><thead><tr><th width="216">Key</th><th width="179.33333333333331">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>includeAgents</code></td><td><code>true</code></td><td>If agents should be included in the result. This parameter is optional. By default, the value is <code>true</code> and the list of agents is returned.</td></tr></tbody></table>

{% hint style="info" %}
The `agents` field will only be returned if the user has the `view-livechat-departments` permission.
{% endhint %}

## Example Call

```powershell
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/livechat/department/iTfLCX3qqwKgf5uqg
```

## Example Response

```json
{
  "department": {
    "_id": "iTfLCX3qqwKgf5uqg",
    "enabled": false,
    "name": "new from api",
    "description": null,
    "numAgents": 1,
    "showOnRegistration": true,
    "_updatedAt": "2016-12-13T17:22:19.109Z"
  },
  "agents": [
    {
      "_id": "DDjZbhTF74n3NBuWK",
      "agentId": "SQafHvoFPuB57NmBD",
      "departmentId": "iTfLCX3qqwKgf5uqg",
      "username": "john.doe",
      "count": 0,
      "order": 0,
      "_updatedAt": "2016-12-13T17:22:19.169Z"
    }
  ],
  "success": true
}
```

## Change Log

| Version | Description                           |
| ------- | ------------------------------------- |
| 2.2.0   | Added `includeAgents` query parameter |
| 0.42.0  | Added                                 |
