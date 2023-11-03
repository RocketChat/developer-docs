# Send Livechat Offline Message

Send the offline message when no agent is available to attend the omnichannel conversation.

<table><thead><tr><th width="163">HTTP Method</th><th width="332">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/livechat/offline.message</code></td><td><code>no</code></td></tr></tbody></table>

## Body

<table><thead><tr><th width="193.33333333333331">Key</th><th width="249">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>name</code><mark style="color:red;"><code>*</code></mark></td><td><code>Livechat Visitor</code></td><td>Message name.</td></tr><tr><td><code>email</code><mark style="color:red;"><code>*</code></mark></td><td><code>visitor@rocket.chat</code></td><td>Visitor email.</td></tr><tr><td><code>message</code><mark style="color:red;"><code>*</code></mark></td><td><code>I need help</code></td><td>Message text.</td></tr><tr><td><code>department</code><mark style="color:red;"><code>*</code></mark></td><td><code>Support</code></td><td>Department name.</td></tr><tr><td><code>host</code><mark style="color:red;"><code>*</code></mark></td><td><code>null</code></td><td>User name of the agent.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location 'http://localrocket:3000/api/v1/livechat/offline.message' \
--header 'Content-Type: application/json' \
--data-raw '{
  "name": "Livechat Visitor",
  "email": "visitor@rocket.chat",
  "message": "I need help",
  "department": "Support",
  "host": "null"
}'
```
{% endcode %}

## Example Result

```javascript
{
  "message": "Livechat offline message sent",
  "success": true
}
```
