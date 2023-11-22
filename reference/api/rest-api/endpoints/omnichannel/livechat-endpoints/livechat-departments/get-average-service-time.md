# Get Average Service Time

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Returns average service time (in seconds) for chats by department.

<table><thead><tr><th width="163">HTTP Method</th><th width="305">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/analytics/departments/average-service-time</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `view-livechat-manager`
{% endhint %}

## Query Parameters

This endpoint supports the `offset` and `count` parameters from the [#pagination](../../../../#pagination "mention")query parameters. The other parameters are as follows:

<table><thead><tr><th width="218.33333333333331">Key</th><th width="240">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>start</code><mark style="color:red;"><code>*</code></mark></td><td><code>2020-09-09T00:11:22.345Z</code></td><td>The start date.</td></tr><tr><td><code>end</code><mark style="color:red;"><code>*</code></mark></td><td><code>2021-09-10T23:59:22.345Z</code></td><td>The end date.</td></tr></tbody></table>

## Example Call

```powershell
curl --location --request GET 'http://localhost:3000/api/v1/livechat/analytics/departments/average-service-time?start=2020-09-09T00:11:22.345Z&end=2021-09-09T00:11:22.345Z \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Example Response

```json
{
    "departments": [
        {
            "_id": "CAJioQNAvLnYWTy8i",
            "averageServiceTimeInSeconds": 1920
        },
        {
            "_id": "GgYvrkAF63aeQmsh4",
            "averageServiceTimeInSeconds": 3583
        },
        {
            "_id": "sLYp3ry7CRizaP3rJ",
            "averageServiceTimeInSeconds": 2941
        },
        {
            "_id": "BiqbQav59HD2LzXEY",
            "averageServiceTimeInSeconds": 5831
        },
        {
            "_id": null,
            "averageServiceTimeInSeconds": 3892998
        },
        {
            "_id": "Yi87Ju7eTHiZQ7CJt",
            "averageServiceTimeInSeconds": 1205
        },
        {
            "_id": "4LCeYmCHHnQ3EDBgf",
            "averageServiceTimeInSeconds": 755
        },
        {
            "_id": "8MGLTfaKLCbE9CqR8",
            "averageServiceTimeInSeconds": 1635
        }
    ],
    "count": 8,
    "offset": 0,
    "total": 8,
    "success": true
}
```
