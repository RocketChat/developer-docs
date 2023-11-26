# Get Agent Departments

Returns the departments associated with an agent.

<table><thead><tr><th width="163">HTTP Method</th><th width="319">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/agents/:agentId/departments</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `view-l-room`
{% endhint %}

## Path Variables

<table><thead><tr><th width="207.33333333333331">Key</th><th width="242">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>agentId</code><mark style="color:red;"><code>*</code></mark></td><td><code>XycfA5CetCPuEjqxw</code></td><td>The agent ID.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request GET 'http://localhost:3000/api/v1/livechat/agents/:agentId/departments \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```
{% endcode %}

## Example Response

```json
{
    "departments": [
        {
            "_id": "R34ZLL6wxDuk4S29G",
            "agentId": "XycfA5CetCPuEjqxw",
            "departmentId": "CAJioQNAvLnYWTy8i",
            "_updatedAt": "2021-06-29T16:09:12.897Z",
            "count": 0,
            "departmentEnabled": true,
            "order": 0,
            "username": "kim.baek"
        },
        {
            "_id": "4TnnwbRsBY2upkzjp",
            "agentId": "XycfA5CetCPuEjqxw",
            "departmentId": "GgYvrkAF63aeQmsh4",
            "_updatedAt": "2021-06-29T16:09:12.918Z",
            "count": 0,
            "departmentEnabled": true,
            "order": 0,
            "username": "kim.baek"
        },
        {
            "_id": "wJTwJsAxRcZ8nc9sB",
            "agentId": "XycfA5CetCPuEjqxw",
            "departmentId": "Yi87Ju7eTHiZQ7CJt",
            "_updatedAt": "2021-06-29T16:09:12.937Z",
            "count": 0,
            "departmentEnabled": false,
            "order": 0,
            "username": "kim.baek"
        },
        {
            "_id": "ccjbvLEREZ6vwjBFk",
            "agentId": "XycfA5CetCPuEjqxw",
            "departmentId": "sLYp3ry7CRizaP3rJ",
            "_updatedAt": "2021-06-29T16:09:12.956Z",
            "count": 0,
            "departmentEnabled": false,
            "order": 0,
            "username": "kim.baek"
        }
    ],
    "success": true
}
```
