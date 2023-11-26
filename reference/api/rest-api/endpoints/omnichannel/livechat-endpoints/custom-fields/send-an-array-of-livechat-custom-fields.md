# Send Array of Custom Field Values

Send an array of values for different custom fields.

<table><thead><tr><th width="163">HTTP Method</th><th width="332">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/livechat/custom.fields</code></td><td><code>no</code></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="215">Key</th><th width="225">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>token</code><mark style="color:red;"><code>*</code></mark></td><td><code>iNKE8a6k6cjbqWhWd</code></td><td>The visitor token.</td></tr><tr><td><code>customFields</code><mark style="color:red;"><code>*</code></mark></td><td><code>"customFields": [{ ... }] }</code></td><td>The object in which you must enter the custom field information.</td></tr><tr><td><code>key</code><mark style="color:red;"><code>*</code></mark></td><td><code>address</code></td><td>The custom field.</td></tr><tr><td><code>value</code><mark style="color:red;"><code>*</code></mark></td><td><code>Rocket.Chat Avenue</code></td><td>The value you want to set for the custom field.</td></tr><tr><td><code>overwrite</code><mark style="color:red;"><code>*</code></mark></td><td><code>true</code></td><td>Overwrite the value of the custom field.</td></tr></tbody></table>

## Example Call

```powershell
curl -X POST \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/livechat/custom.fields \
     -d '{"token": "iNKE8a6k6cjbqWhWd", 
     "customFields": [{
          "key": "address", 
          "value": "Rocket.Chat Avenue", 
          "overwrite": true}]}'
```

## Example Response

```json
{
  "fields": [
    {
      "Key": "address",
      "value": "Rocket.Chat Avenue",
      "overwrite": true
    }
  ],
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.70.0  | Added       |
