# Get Status of Agents

Retrieves the number of agents for each status.

<table><thead><tr><th width="163">HTTP Method</th><th width="332">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/analytics/dashboards/charts/agents-status</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `view-livechat-manager`
{% endhint %}

## Query Parameters

<table><thead><tr><th width="208.33333333333331">Key</th><th width="242">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>departmentId</code></td><td><code>CAJioQNAvLnYWTy8i</code></td><td>The department ID. This parameter is optional.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request GET 'http://localhost:3000/api/v1/api/v1/livechat/analytics/dashboards/charts/agents-status\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```
{% endcode %}

## Example Response

```json
{
    "_id": null,
    "offline": 78,
    "away": 5,
    "busy": 0,
    "available": 3,
    "success": true
}
```
