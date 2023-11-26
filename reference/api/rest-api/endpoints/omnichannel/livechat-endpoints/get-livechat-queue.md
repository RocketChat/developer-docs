# Get Livechat Queue

<table><thead><tr><th width="163">HTTP Method</th><th width="332">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/queue</code></td><td><a href="../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `view-l-room`
{% endhint %}

## Query Parameters

This endpoint supports the optional [#pagination](../../../#pagination "mention") parameters. Other optional parameters are as follows:

<table><thead><tr><th>Key</th><th width="234.33333333333331">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>includeOfflineAgents</code></td><td><code>true</code></td><td>Whether you want to include offline agents or not.</td></tr><tr><td><code>agentId</code></td><td><code>aobEdbYhXfu5dsd9</code></td><td>The agent ID.</td></tr><tr><td><code>departmentId</code></td><td><code>3n2kj3n2j3fu5hkeqG</code></td><td>The department ID.</td></tr></tbody></table>

## Example Call

```powershell
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/livechat/queue?includeOfflineAgents=true
```

## Example Response

```json
{
    "queue": [
    {
      "chats": 1,
      "user": {
        "_id": "CaevAPDbXN252kyXa",
        "username": "marcos.defendi",
        "status": "online"
      },
      "department": {
        "_id": "457diLwcQMmdpaTjo",
        "name": "Department 1"
      }
    },
    {
      "chats": 2,
      "user": {
        "_id": "CaevAPDbXN252kyXa",
        "username": "marcos.defendi",
        "status": "online"
      },
      "department": {
        "_id": "5mt9oEtQxuMMH23Co",
        "name": "Department 2"
      }
    }
  ],
  "count": 2,
  "offset": 0,
  "total": 2,
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 2.4.0   | Added       |
