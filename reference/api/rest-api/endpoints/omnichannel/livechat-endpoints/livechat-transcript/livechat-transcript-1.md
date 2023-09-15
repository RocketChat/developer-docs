# Send Livechat Transcript

This endpoint is used by agents and managers to schedule an email transcript to be sent once the chat is closed.&#x20;

{% hint style="info" %}
* It requires the `send-omnichannel-chat-transcript` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
* The room must be opened.
{% endhint %}

| URL                                | Requires Auth | HTTP Method |
| ---------------------------------- | ------------- | ----------- |
| `/api/v1/livechat/transcript/:rid` | `YES`         | `POST`      |

## Path Parameters

<table><thead><tr><th width="162">Argument</th><th width="277">Example</th><th width="149">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>rid</code></td><td><code>tcbbSmWSLR5uo5PBW</code></td><td>Required</td><td>The Id of the Live Chat room.</td></tr></tbody></table>

## Payload Parameters

<table><thead><tr><th width="162">Argument</th><th width="277">Example</th><th width="149">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>email</code></td><td><code>fim@rocket.chat</code></td><td>Required</td><td>The email address where   the transcript should be sent.</td></tr><tr><td>subject</td><td><code>Test request Transcript</code></td><td>Required</td><td>The subject of the email.</td></tr></tbody></table>

## Example Payload

```json
{
    "email":"fim@rocket.chat",
    "subject":"Test request Transcript"
}
```

## Example Call

```bash
curl -L -X POST 'http://localhost:3000/api/v1/livechat/transcript/AHsFiNLYWQK35jgtS" \
-H 'x-auth-token: qlHA60g5JQjJJG7C_8MgXoFnOiRQ8X9TWVVq4AcQeFb' \
-H 'x-user-id: rbAXPnMktTFbNpwtJ' \
-H 'Content-Type: application/json' \
--data-raw '{
    "email":"funke.olasupo@rocket.chat",
    "subject":"Livechat Transcript"
}'
```

## Example Result

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
* **Transcript Requested:** Occurs when a transcript has been requested for this room. See [livechat-transcript-2.md](livechat-transcript-2.md "mention") and delete the current request before requesting for the transcript again.

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
