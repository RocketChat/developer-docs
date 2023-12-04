# Get Call Center Queue Membership Information

<table><thead><tr><th width="163">HTTP Method</th><th width="337">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/voip/queues.getQueuedCallsForThisExtension</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `inbound-voip-calls`
{% endhint %}

## Query Parameters

<table><thead><tr><th width="205.33333333333331">Key</th><th width="231">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>extension</code><mark style="color:red;"><code>*</code></mark></td><td><code>12234</code></td><td>The phone extension for VoIP.</td></tr></tbody></table>

## Example Call <a href="#example-call" id="example-call"></a>

{% code overflow="wrap" %}
```powershell
curl --location 'http://localhost:3000/api/v1/voip/queues.getQueuedCallsForThisExtension?extension=12234' \
--header 'X-Auth-Token: NcQtu58azANDJ1FuCmGvGVO' \
--header 'X-User-Id: CkCPNcvsvCDfmWL'
```
{% endcode %}

## Example Response <a href="#example-result" id="example-result"></a>

```json
{
  "extension": "12234",
  "queueCount": "1",
  "callWaitingCount": "2"
 }
```
