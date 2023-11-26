# Get History of Agents Available for Service

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Return the list of agents and their available time for the provided time frame.

<table><thead><tr><th width="163">HTTP Method</th><th width="319">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/analytics/agents/available-for-service-history</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `view-livechat-manager`
{% endhint %}

## Query Parameters

This endpoint supports the optional `offset` and `count` parameters from the [#pagination](../../../../#pagination "mention")query parameters. The other parameters are as follows:

<table><thead><tr><th width="208.33333333333331">Key</th><th width="221">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>start</code><mark style="color:red;"><code>*</code></mark></td><td><code>2020-09-09T00:11:22.345Z</code></td><td>start date</td></tr><tr><td><code>end</code><mark style="color:red;"><code>*</code></mark></td><td><code>2020-09-10T23:59:22.345Z</code></td><td>end date</td></tr><tr><td><code>fullReport</code></td><td><code>true</code></td><td>If set to <code>true</code>, it shares the service history which will contain more granular data such as the time of the day the agent was available.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request GET 'http://localhost:3000/api/v1/livechat/analytics/agents/available-for-service-history?start=2020-09-09T00:11:22.345Z&end=2020-09-10T23:59:22.345Z' \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```
{% endcode %}

## Example Response

The response without the `fullReport` flag set to `false`. It only returns high-level consolidated data about the total available time for each agent within the specified duration.

```json
{
    "agents": [
        {
            "availableTimeInSeconds": 102117,
            "username": "kim.chaeyu"
        },
        {
            "availableTimeInSeconds": 280,
            "username": "bruna.mar"
        },
        {
            "availableTimeInSeconds": 40242,
            "username": "marina.dia"
        },
        {
            "availableTimeInSeconds": 1,
            "username": "ro.kim"
        }
    ],
    "count": 4,
    "offset": 0,
    "total": 4,
    "success": true
}
```

The response with the `fullReport` flag set to `true`. It contains an extra property `serviceHistory`.

```json
{
    "agents": [
        {
            "serviceHistory": [
                {
                    "startedAt": "2021-11-24T08:35:49.058Z",
                    "stoppedAt": "2021-11-24T08:41:32.721Z"
                },
                {
                    "startedAt": "2021-11-24T08:51:15.623Z",
                    "stoppedAt": "2021-11-24T08:53:59.707Z"
                },
                {
                    "startedAt": "2021-11-24T08:55:45.128Z",
                    "stoppedAt": "2021-11-24T08:55:45.214Z"
                },
                {
                    "startedAt": "2021-11-24T16:56:35.486Z",
                    "stoppedAt": "2021-11-24T17:05:56.611Z"
                },
                {
                    "startedAt": "2021-11-24T17:20:26.066Z",
                    "stoppedAt": "2021-11-24T18:29:59.000Z"
                }
            ],
            "availableTimeInSeconds": 2115334,
            "username": "doe.john"
        },
        {
            "serviceHistory": [
                {
                    "startedAt": "2022-02-06T09:45:26.476Z",
                    "stoppedAt": "2022-02-06T09:45:27.499Z"
                },
                {
                    "startedAt": "2022-02-06T09:45:28.083Z",
                    "stoppedAt": "2022-02-06T09:45:28.663Z"
                },
                {
                    "startedAt": "2022-02-06T09:45:29.117Z",
                    "stoppedAt": "2022-02-06T09:45:29.672Z"
                },
                {
                    "startedAt": "2022-02-06T09:45:30.129Z",
                    "stoppedAt": "2022-02-06T09:45:30.534Z"
                },
                {
                    "startedAt": "2022-02-06T09:45:30.923Z",
                    "stoppedAt": "2022-02-06T09:45:31.714Z"
                },
                {
                    "startedAt": "2022-02-06T09:45:39.037Z",
                    "stoppedAt": "2022-02-06T09:45:41.680Z"
                }
            ],
            "availableTimeInSeconds": 7586,
            "username": "white.chris"
        },
        {
            "serviceHistory": [
                {
                    "startedAt": "2021-12-27T13:25:44.459Z",
                    "stoppedAt": "2021-12-27T13:27:11.208Z"
                }
            ],
            "availableTimeInSeconds": 1508,
            "username": "max.yui"
        }
    ],
    "count": 3,
    "offset": 0,
    "total": 3,
    "success": true
}
```
