# Get Average Waiting Time

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Gives the average visitor waiting time (in seconds) by department.

<table><thead><tr><th width="163">HTTP Method</th><th width="305">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/analytics/departments/average-waiting-time</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `view-livechat-manager`
{% endhint %}

## Query Parameters

This endpoint supports the `offset` and `count` parameters from the [#pagination](../../../../#pagination "mention")query parameters. The other parameters are as follows:

<table><thead><tr><th width="206.33333333333331">Key</th><th width="249">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>start</code><mark style="color:red;"><code>*</code></mark></td><td><code>2020-09-09T00:11:22.345Z</code></td><td>The start date.</td></tr><tr><td><code>end</code><mark style="color:red;"><code>*</code></mark></td><td><code>2020-09-10T23:59:22.345Z</code></td><td>The end date.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request GET 'http://localhost:3000/api/v1/livechat/analytics/departments/average-waiting-time?start=2020-02-12T00:11:22.345Z&end=2020-02-18T23:59:22.345Z' \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```
{% endcode %}

## Example Response

```json
{
    "departments": [
        {
            "_id": "64181a0728384134ed600dcc",
            "averageWaitingTimeInSeconds": 199
        },
        {
            "_id": "649230d479f5c6e276cf4a12",
            "averageWaitingTimeInSeconds": 521
        },
        {
            "_id": null,
            "averageWaitingTimeInSeconds": 1216
        }
    ],
    "count": 3,
    "offset": 0,
    "total": 3,
    "success": true
}
```
