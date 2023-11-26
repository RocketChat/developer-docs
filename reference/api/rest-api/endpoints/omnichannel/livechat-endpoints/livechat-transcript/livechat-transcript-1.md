# Send Livechat Transcript

This endpoint is used by agents and managers to schedule an email transcript to be sent once the chat is closed.&#x20;

{% hint style="info" %}
* It requires the `send-omnichannel-chat-transcript` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
* The room must be opened.
{% endhint %}

<table><thead><tr><th width="163">HTTP Method</th><th width="305">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/livechat/transcript/:rid</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Path Variables

<table><thead><tr><th width="162">Key</th><th width="258">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>rid</code><mark style="color:red;"><code>*</code></mark></td><td><code>tcbbSmWSLR5uo5PBW</code></td><td>The room ID.</td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="162">Key</th><th width="270">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>email</code><mark style="color:red;"><code>*</code></mark></td><td><code>fim@rocket.chat</code></td><td>The email address where the transcript should be sent.</td></tr><tr><td><code>subject</code><mark style="color:red;"><code>*</code></mark></td><td><code>Test request Transcript</code></td><td>The subject of the email.</td></tr></tbody></table>

## Example Call

```powershell
curl -L -X POST 'http://localhost:3000/api/v1/livechat/transcript/AHsFiNLYWQK35jgtS" \
-H 'x-auth-token: qlHA60g5JQjJJG7C_8MgXoFnOiRQ8X9TWVVq4AcQeFb' \
-H 'x-user-id: rbAXPnMktTFbNpwtJ' \
-H 'Content-Type: application/json' \
--data-raw '{
    "email":"funke@test.com",
    "subject":"Livechat Transcript"
}'
```

## Example Response

### Success

```javascript
{
  "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **No Permission**: Occurs when the authenticated user doesn't have `send-omnichannel-chat-transcript` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
* **Transcript Requested:** Occurs when a transcript has been requested for this room. See [livechat-transcript-2.md](livechat-transcript-2.md "mention") and delete the current request before requesting the transcript again.

{% tabs %}
{% tab title="Authorization" %}
```json
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}

{% tab title="No Permission" %}
```json
{
    "success": false,
    "error": "User does not have the permissions required for this action [error-unauthorized]"
}
```
{% endtab %}

{% tab title="Transcript Requested" %}
```json
{
    "success": false,
    "error": "Transcript already requested [error-transcript-already-requested]",
    "errorType": "error-transcript-already-requested"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 6.4.0   | Added       |
