# Get Total Abandoned Chats

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Gives the total number of abandoned chats (rooms) by department.

<table><thead><tr><th width="163">HTTP Method</th><th width="305">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>api/v1/livechat/analytics/departments/total-abandoned-chats</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `view-livechat-manager`
{% endhint %}

## Query Parameters

This endpoint supports the `offset` and `count` parameters from the [#pagination](../../../../#pagination "mention")query parameters. The other parameters are as follows:

<table><thead><tr><th width="201.33333333333331">Key</th><th>Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>start</code><mark style="color:red;"><code>*</code></mark></td><td><code>2020-09-09T00:11:22.345Z</code></td><td>The start date.</td></tr><tr><td><code>end</code><mark style="color:red;"><code>*</code></mark></td><td><code>2021-09-10T23:59:22.345Z</code></td><td>The end date.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request GET 'http://localhost:3000/api/v1/livechat/analytics/departments/total-abandoned-chats?start=2020-09-10T23:59:22.345Z&end=2021-09-10T23:59:22.345Z' \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```
{% endcode %}

## Example Response

```json
{
    "departments": [
        {
            "abandonedRooms": 3,
            "_id": "4LCeYmCHHnQ3EDBgf"
        },
        {
            "abandonedRooms": 1,
            "_id": "8MGLTfaKLCbE9CqR8"
        },
        {
            "abandonedRooms": 1,
            "_id": "Yi87Ju7eTHiZQ7CJt"
        },
        {
            "abandonedRooms": 77,
            "_id": "GgYvrkAF63aeQmsh4"
        },
        {
            "abandonedRooms": 12,
            "_id": "sLYp3ry7CRizaP3rJ"
        },
        {
            "abandonedRooms": 12,
            "_id": "BiqbQav59HD2LzXEY"
        },
        {
            "abandonedRooms": 6,
            "_id": "CAJioQNAvLnYWTy8i"
        }
    ],
    "count": 7,
    "offset": 0,
    "total": 7,
    "success": true
}
```
