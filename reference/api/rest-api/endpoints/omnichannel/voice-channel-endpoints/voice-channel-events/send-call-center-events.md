# Send Call Center Events

Send the VoIP client events.

<table><thead><tr><th width="163">HTTP Method</th><th width="334">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/voip/events</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `view-l-room`
{% endhint %}

## Body Parameters

<table><thead><tr><th width="187.33333333333331">Key</th><th width="209">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>rid</code><mark style="color:red;"><code>*</code></mark></td><td><code>c9YW3rejo7HeL6ZDW</code></td><td>The room ID.</td></tr><tr><td><code>event</code><mark style="color:red;"><code>*</code></mark></td><td><code>string</code></td><td>List of VoIP client events.</td></tr><tr><td><code>comment</code></td><td><code>string</code></td><td>The comment.</td></tr></tbody></table>

### VoIP Client Events

List of VoIP client Events available in enum format.

```json
{
	"VOIP-CALL-STARTED" = "voip-call-started",
	"VOIP-CALL-ENDED" = "voip-call-ended",
	"VOIP-CALL-DECLINED" = "voip-call-declined",
	"VOIP-CALL-ON-HOLD" = "voip-call-on-hold",
	"VOIP-CALL-UNHOLD" = "voip-call-unhold",
	"VOIP-CALL-DURATION" = "voip-call-duration",
}
```

## Example Call <a href="#example-call" id="example-call"></a>

```json
curl --location --request POST 'localhost:3000/api/v1/voip/events' \
--header 'X-Auth-Token: aEoKaT8qus3IZHlr_OlAzcsnz46SzZLJeqoRbbctcDQ' \
--header 'X-User-Id: 6vHSSqdBHdm2R4gfi' \
--header 'Content-Type: application/json' \
--data-raw '{
    "rid": "oWLW6v8c8oRGb4cC9",
    "event": "voip-call-started"
}'
```
