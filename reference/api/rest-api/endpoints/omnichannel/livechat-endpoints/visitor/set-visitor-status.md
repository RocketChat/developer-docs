---
description: Sets omnichannel visitor's satus
---

# Set Visitor Status

Set Omnichannel visitor's status.

<table><thead><tr><th width="163">HTTP Method</th><th width="349">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/livechat/visitor.status</code></td><td><code>no</code></td></tr></tbody></table>

## Body

<table><thead><tr><th width="224.33333333333331">Key</th><th>Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>token</code><mark style="color:red;"><code>*</code></mark></td><td><code>8s7e9ony6ctl27e1qf8kue</code></td><td>The visitor token.</td></tr><tr><td><code>status</code><mark style="color:red;"><code>*</code></mark></td><td><code>busy</code></td><td>The status of the visitor.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location 'https://writing-demo.dev.rocket.chat/api/v1/livechat/visitor.status' \
--header 'Content-Type: application/json' \
--data '{
    "token": "54fc5544030bcecda0533",
    "status": "busy"
}'
```
{% endcode %}

## Example Response

```javascript
{
    "token": "54fc5544030bcecda0533",
    "status": "busy",
    "success": true
}
```
