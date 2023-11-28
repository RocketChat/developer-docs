# Get Inquiries List

Lists all open Livechat inquiries.

<table><thead><tr><th width="163">HTTP Method</th><th width="347">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/inquiries.list</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
* An incoming chat that has not yet been taken by the agent is called an **inquiry**. After it's been taken by the agent it is referred to as **room**.
* Permission required: `view-livechat-manager`
{% endhint %}

## Query Parameters

This endpoint supports the optional [#pagination](../../../../#pagination "mention") parameters. Other optional parameters are as follows:

<table><thead><tr><th width="197.33333333333331">Key</th><th width="239">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>department</code></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The department ID or name.</td></tr></tbody></table>

## Example Call

```powershell
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/livechat/inquiries.list
```

## Example Response

```json
{
    "inquiries": [
          {
            "_id": "GpxfRo8TaPHfsnnC5",
            "rid": "EbQjtCosHJWLQmQYT",
            "name": "Marcos Defendi",
            "ts": "2019-06-11T19:01:57.424Z",
            "status": "queued"
        }
    ],
    "offset": 0,
    "count": 1,
    "total": 1,
    "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 1.2.0   | Added       |
