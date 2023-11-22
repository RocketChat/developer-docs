# Get Percentage of Abandoned Chats

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Gives the percentage of abandoned chats per department.

<table><thead><tr><th width="163">HTTP Method</th><th width="305">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/analytics/departments/percentage-abandoned-chats</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `view-livechat-manager`
{% endhint %}

## Query Parameters

This endpoint supports the `offset` and `count` parameters from the [#pagination](../../../../#pagination "mention")query parameters. The other parameters are as follows:

<table><thead><tr><th width="188.33333333333331">Key</th><th>Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>start</code><mark style="color:red;"><code>*</code></mark></td><td><code>2020-09-09T00:11:22.345Z</code></td><td>The start date.</td></tr><tr><td><code>end</code><mark style="color:red;"><code>*</code></mark></td><td><code>2020-09-10T23:59:22.345Z</code></td><td>The end date.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request GET 'http://localhost:3000//api/v1/livechat/analytics/departments/percentage-abandoned-chats?start=2020-02-12T00:11:22.345Z&end=2020-02-18T23:59:22.345Z' \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```
{% endcode %}

## Example Response

```json
{
    "departments": [
        {
            "_id": "64cf6c6feb07a913d946f34d",
            "percentageOfAbandonedChats": 0
        },
        {
            "_id": null,
            "percentageOfAbandonedChats": 0
        },
        {
            "_id": "649230d479f5c6e276cf4a12",
            "percentageOfAbandonedChats": 0
        },
        {
            "_id": "64181a0728384134ed600dcc",
            "percentageOfAbandonedChats": 11
        }
    ],
    "count": 4,
    "offset": 0,
    "total": 4,
    "success": true
}
```
