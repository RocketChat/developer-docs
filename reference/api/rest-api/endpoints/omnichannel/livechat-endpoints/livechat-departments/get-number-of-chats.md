# Get Number of Chats

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Gives the number of chat rooms by department.

<table><thead><tr><th width="163">HTTP Method</th><th width="305">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/analytics/departments/amount-of-chats</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `view-livechat-manager`
{% endhint %}

## Query Parameters

This endpoint supports the `offset` and `count` parameters from the [#pagination](../../../../#pagination "mention")query parameters. The other parameters are as follows:

<table><thead><tr><th width="210.33333333333331">Key</th><th width="246">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>start</code><mark style="color:red;"><code>*</code></mark></td><td><code>2020-09-09T00:11:22.345Z</code></td><td>The start date.</td></tr><tr><td><code>end</code><mark style="color:red;"><code>*</code></mark></td><td><code>2021-09-10T23:59:22.345Z</code></td><td>The end date.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request GET 'http://localhost:3000/api/v1/livechat/analytics/departments/amount-of-chats?start=2020-01-10T23:59:22.345Z&end=2021-02-10T23:59:22.345Z \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```
{% endcode %}

## Example Response

```json
{
    "departments": [
        {
            "rooms": 30,
            "_id": null
        },
        {
            "rooms": 486,
            "_id": "GgYvrkAF63aeQmsh4"
        },
        {
            "rooms": 13,
            "_id": "qajzu7WaBRoQBpq6Z"
        },
        {
            "rooms": 2,
            "_id": "Z2KWYBJQFR7AzfmQL"
        },
        {
            "rooms": 61,
            "_id": "BiqbQav59HD2LzXEY"
        },
        {
            "rooms": 1,
            "_id": "NJaMpSvZFZ4NAXm3j"
        },
        {
            "rooms": 181,
            "_id": "CAJioQNAvLnYWTy8i"
        },
        {
            "rooms": 6,
            "_id": "YiWdMkdbFhk3o9daf"
        },
        {
            "rooms": 10,
            "_id": "8MGLTfaKLCbE9CqR8"
        },
        {
            "rooms": 4,
            "_id": "MpAiP9PMyHwBcmALx"
        },
        {
            "rooms": 51,
            "_id": "Yi87Ju7eTHiZQ7CJt"
        }
    ],
    "count": 11,
    "offset": 0,
    "total": 11,
    "success": true
}
```
