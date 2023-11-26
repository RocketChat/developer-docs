# Get Chat Metrics

Retrieves information about the chats.

<table><thead><tr><th width="163">HTTP Method</th><th width="332">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/analytics/dashboards/chats-totalizers</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `view-livechat-manager`
{% endhint %}

## Query Parameters

<table><thead><tr><th width="208.33333333333331">Key</th><th width="242">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>start</code><mark style="color:red;"><code>*</code></mark></td><td><code>2021-07-20T19:00:00.000Z</code></td><td>The start time.</td></tr><tr><td><code>end</code><mark style="color:red;"><code>*</code></mark></td><td><code>2021-07-21T18:59:59.000Z</code></td><td>The end time.</td></tr><tr><td><code>departmentId</code></td><td><code>CAJioQNAvLnYWTy8i</code></td><td>The department ID. This parameter is optional.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request GET 'http://localhost:3000/api/v1/livechat/analytics/dashboards/chats-totalizers?departmentId=CAJioQNAvLnYWTy8i&start=2021-07-20T19:00:00.000Z&end=2021-07-21T18:59:59.000Z\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```
{% endcode %}

## Example Response

```json
{
    "totalizers": [
        {
            "title": "Total_abandoned_chats",
            "value": 1
        },
        {
            "title": "Avg_of_abandoned_chats",
            "value": "11%"
        },
        {
            "title": "Avg_of_chat_duration_time",
            "value": "01:24:56"
        }
    ],
    "success": true
}
```
