# Get Conversations by Status

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

View the metrics of omnichannel conversations in your workspace during a selected time range based on their status: **Open**, **Queued**, **On Hold**, or **Closed**

<table><thead><tr><th width="163">HTTP Method</th><th width="332">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/analytics/dashboards/conversations-by-status</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `view-livechat-reports`
{% endhint %}

## Query Parameters

<table><thead><tr><th width="163">Key</th><th width="332">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>start</code><mark style="color:red;"><code>*</code></mark></td><td><code>2023-11-28T00:11:22.345Z</code></td><td>The start time.</td></tr><tr><td><code>end</code><mark style="color:red;"><code>*</code></mark></td><td><code>2023-11-29T00:11:22.345Z</code></td><td>The end time.</td></tr></tbody></table>

## Example Call

```powershell
curl --location --request GET 'http://localhost:3000/api/v1/livechat/priorities\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-id'
```

## Example Response

```json
{
    "total": 25,
    "data": [
        {
            "label": "Closed",
            "value": 24
        },
        {
            "label": "Open",
            "value": 1
        },
        {
            "label": "Queued",
            "value": 0
        },
        {
            "label": "On_Hold",
            "value": 0
        }
    ],
    "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 6.4.0   | Added       |
