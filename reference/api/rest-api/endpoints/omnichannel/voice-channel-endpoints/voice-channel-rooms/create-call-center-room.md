# Create Call Center Room

Creates a VoIP room if the room ID is not passed; otherwise, it gets an existing room based on the room ID and token.

<table><thead><tr><th width="163">HTTP Method</th><th width="307">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/voip/room</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `inbound-voip-calls`
{% endhint %}

## Query Parameters

<table><thead><tr><th width="200">Key</th><th width="217">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>token</code><mark style="color:red;"><code>*</code></mark></td><td><code>867ad6a09fc4af29f6f1f2a9cf1deaba</code></td><td>The visitor token.</td></tr><tr><td><code>agentId</code><mark style="color:red;"><code>*</code></mark></td><td><code>6vHSSqdBHdm2</code></td><td>The agent ID.</td></tr><tr><td><code>direction</code></td><td><code>inbound</code></td><td>The direction of the call.</td></tr><tr><td><code>rid</code></td><td><code>jiuriewcnm2R4gfi</code></td><td>The room ID.</td></tr></tbody></table>

## Example Call <a href="#example-call" id="example-call"></a>

{% code overflow="wrap" %}
```powershell
curl --location 'http://localhost:3000/api/v1/voip/room?token=867ad6a09fc4af29f6f1f2a9cf1deaba%26agentId%3D6vHSSqdBHdm2R4gfi&agentId=6vHSSqdBHdm2R4gfi' \
--header 'X-Auth-Token: NcQtu58azANDJGqhK9h-j61l' \
--header 'X-User-Id: CkCPNcvsvCDfmWLqC'
```
{% endcode %}

## Example Response

```json
{
    "success": true
}
```
