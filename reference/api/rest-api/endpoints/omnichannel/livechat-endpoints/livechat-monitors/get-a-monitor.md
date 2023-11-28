# Get a Monitor

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Get details of a specific monitor.

<table><thead><tr><th width="163">HTTP Method</th><th width="332">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/monitors/:username</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `manage-livechat-monitors`
{% endhint %}

## Path Variables

<table><thead><tr><th width="216.33333333333331">Key</th><th width="220">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>username</code><mark style="color:red;"><code>*</code></mark></td><td><code>1-agent</code></td><td>The username of the person monitoring.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request GET 'http://localhost:3000/api/v1/livechat/monitors/1-agent' \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```
{% endcode %}

## Example Response

```json
{
    "_id": "RSb7exHJsiKqwRjPF",
    "username": "1-agent",
    "emails": [
        {
            "address": "1-agent@g.c",
            "verified": false
        }
    ],
    "status": "offline",
    "name": "1-agent",
    "statusLivechat": "not-available",
    "livechat": {
        "maxNumberSimultaneousChat": "4"
    },
    "success": true
}
```
