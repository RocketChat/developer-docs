# Close Call Center Room

<table><thead><tr><th width="163">HTTP Method</th><th width="307">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/voip/room.close</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `inbound-voip-calls`
{% endhint %}

## Body Parameters

<table><thead><tr><th width="163">Key</th><th width="259">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>rid</code></td><td><code>c9YW3rejo7HeL6ZDW</code></td><td>The ID of the open room.</td></tr><tr><td><code>token</code></td><td><code>yHoawq4s9bDn4dM5H</code></td><td>The visitor token.</td></tr></tbody></table>

## Example Call <a href="#example-call" id="example-call"></a>

```powershell
curl --location --request POST 'localhost:3000/api/v1/voip/room.close' \
--header 'X-Auth-Token: aEoKaT8qus3IZHlr_OlAzcsnz46SzZLJeqoRbbctcDQ' \
--header 'X-User-Id: 6vHSSqdBHdm2R4gfi' \
--header 'Content-Type: application/json' \
--data-raw '{
    "rid": "c9YW3rejo7HeL6ZDW",
    "token": "yHoawq4s9bDn4dM5H"
}'
```

## Example Response

```json
{
    "rid": "c9YW3rejo7HeL6ZDW",
}
```
