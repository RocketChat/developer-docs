# Request PDF Transcript

<figure><img src="../../../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

[Request a PDF transcript ](https://docs.rocket.chat/use-rocket.chat/omnichannel-agents-guides/omnichannel-conversation#to-export-the-transcript-as-pdf)for an Omnichannel conversation.

{% hint style="info" %}
* The conversation must be closed before it can be exported.
* It requires the `request-pdf-transcript` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions). Omnichannel [managers](https://docs.rocket.chat/use-rocket.chat/omnichannel/managers) and [agents](https://docs.rocket.chat/use-rocket.chat/omnichannel/agents) have this permission by default.
{% endhint %}

<table><thead><tr><th width="356.3333333333333">URL</th><th>Requires Auth</th><th>HTTP Method</th></tr></thead><tbody><tr><td><code>omnichannel/:rid/request-transcript</code></td><td><code>YES</code></td><td><code>POST</code></td></tr></tbody></table>

## Headers

<table><thead><tr><th width="179">Argument</th><th width="169">Example</th><th width="143">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>X-User-Id</code></td><td><code>myuser-name</code></td><td>Required</td><td>The authenticated user ID.</td></tr><tr><td><code>X-Auth-Token</code></td><td><code>myauth-token</code></td><td>Required</td><td>Auth token.</td></tr></tbody></table>

## Path Parameters

<table><thead><tr><th width="152">Argument</th><th width="277">Example</th><th width="149">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>rid</code></td><td><code>gLanBL8wSfXG7AqBo</code></td><td>Required</td><td>The <code>rid</code> of the Omnichannel room.</td></tr></tbody></table>

## Example Call

```bash
curl --location --request POST 'http://localhost:3000/api/v1/omnichannel/teSNo3QPv4ebudmab/request-transcript' \
--header 'x-auth-token: fjiPBhtyFAn5JO3RDdDvKjkXToV2pd4_lb-nkdgJ_Q4' \
--header 'x-user-id: rbAXPnMktTFbNpwtJ'
```

## Example Result

### Success

```json
{
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **Invalid Room:** This occurs when the `rid` does not exist in the workspace.
* **Room still open**: This happens when the room you're requesting a transcript for is still open. Only closed conversations can be exported.
* **No Permission**: This occurs when the authenticated user doesn't have the  `request-pdf-transcript` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
* **Can't Access Room**: Occurs when the authenticated user doesn't have access to the conversation room.

{% tabs %}
{% tab title=" Authorization" %}
```json
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}

{% tab title="Invalid Room" %}
```json
{
    "success": false,
    "error": "error-invalid-room"
}
```
{% endtab %}

{% tab title="Room still open" %}
```json
{
    "success": false,
    "error": "room-still-open"
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

{% tab title="Can't Access Room" %}
```bash
{
    "success": false,
    "error": "error-not-allowed"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 6.0.0   | Added       |
