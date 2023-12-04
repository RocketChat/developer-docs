# Get Voice Channel Queue Summary

<table><thead><tr><th width="163">HTTP Method</th><th width="337">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/voip/queues.getSummary</code></td><td><a href="../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `inbound-voip-calls`
{% endhint %}

## Example Call

```powershell
curl --location --request GET 'localhost:3000/api/v1/voip/queues.getSummary' \
--header 'X-Auth-Token: aEoKaT8qus3IZHlr_OlAzcsnz46SzZLJeqoRbbctcDQ' \
--header 'X-User-Id: 6vHSSqdBHdm2R4gfi' \
--header 'Content-Type: application/json' 
```

## Example Response

```json
{
	"name": "string",
	"loggedin": "string",
	"available": "string",
	"callers": "string",
	"holdtime": "string",
	"talktime": "string",
	"logestholdtime": "string"
}
```
