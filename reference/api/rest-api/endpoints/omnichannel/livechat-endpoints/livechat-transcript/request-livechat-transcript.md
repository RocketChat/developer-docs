# Request Livechat Transcript

The endpoint is used by visitors to request a transcript of their chat to be sent to their email once the conversation ends.

{% hint style="info" %}
The room must be closed before you can send a transcript.
{% endhint %}

<table><thead><tr><th width="163">HTTP Method</th><th width="305">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/livechat/transcript</code></td><td><code>no</code></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="206.33333333333331">Key</th><th width="255">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>rid</code><mark style="color:red;"><code>*</code></mark></td><td><code>XFzMqgn33DcsQkpJp</code></td><td>The room ID.</td></tr><tr><td><code>token</code><mark style="color:red;"><code>*</code></mark></td><td><code>iNKE8a6k6cjbqWhWd</code></td><td>The visitor token.</td></tr><tr><td><code>email</code><mark style="color:red;"><code>*</code></mark></td><td><code>visitor@rocket.chat</code></td><td>The visitor's email ID where the transcript should be sent.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl -X POST \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/livechat/transcript \
     -d '{"rid":"XFzMqgn33DcsQkpJp", 
          "token": "iNKE8a6k6cjbqWhWd", 
          "email": "visitor@rocket.chat"}'
```
{% endcode %}

## Example Response

```json
{
  "message": "Livechat transcript sent",
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.70.0  | Added       |
