# Get Agents of Department

Get the agents of a specific department.

<table><thead><tr><th width="163">HTTP Method</th><th width="305">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/department/:_id/agents</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permissions required:

* `view-livechat-departments`
* `view-l-room`
{% endhint %}

## Query Parameters

This endpoints supports the [#pagination](../../../../#pagination "mention") query parameters.

## Path Variables

<table><thead><tr><th width="219.33333333333331">Key</th><th width="224">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>_id</code><mark style="color:red;"><code>*</code></mark></td><td><code>BiqbQav59HD2LzXEY</code></td><td>The department ID.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location 'https://writing-demo.dev.rocket.chat/api/v1/livechat/department/649230d479f5c6e272/agents' \
--header 'X-Auth-Token: oKUJdR1jFvJ7kNEIYBqAX' \
--header 'X-User-Id: CkCPNcvsvCDfmWLqC'
```
{% endcode %}

## Example Response

```json
{
    "agents": [
        {
            "_id": "SWugWdHhcTX4G2NAP",
            "agentId": "rocket.cat",
            "departmentId": "BiqbQav59HD2LzXEY",
            "_updatedAt": "2021-07-14T14:58:01.013Z",
            "count": 17,
            "departmentEnabled": true,
            "order": 0,
            "username": "rocket.cat"
        }
    ],
    "count": 1,
    "offset": 0,
    "total": 1,
    "success": true
}
```
