# Set SLA Policy to Inquiry

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Set [SLA policy ](https://docs.rocket.chat/use-rocket.chat/omnichannel/sla-policies)to an inquiry.

{% hint style="info" %}
* It requires either the `view-l-room` or `manage-livechat-sla` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
* You can only set the policy for an inquiry that has not been taken by an agent.
{% endhint %}

<table><thead><tr><th width="163">HTTP Method</th><th width="347">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>PUT</code></td><td><code>/api/v1/livechat/inquiry.setSLA</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="189">Key</th><th>Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>ZDYMFPpvnXgptmzMs</code></td><td>The room ID.</td></tr><tr><td><code>sla</code><mark style="color:red;"><code>*</code></mark></td><td><code>6417f67528384134ed600dc6</code></td><td>Name or ID of the SLA policy.</td></tr></tbody></table>

## Example Call

```powershell
curl --location --request PUT 'http://localhost:3000/api/v1/livechat/inquiry.setSLA' \
--header 'x-auth-token: fjiPBhtyFAn5JO3RDdDvKjkXToV2pd4_lb-nkdgJ_Q4' \
--header 'x-user-id: rbAXPnMktTFbNpwtJ' \
--data '{
    "roomId":"ZDYMFPpvnXgptmzMs",
    "sla":"6417f67528384134ed600dc6"
}'
```

## Example Response

### Success

```json
{
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **No Permission**: Occurs when the authenticated user neither has the `view-l-room` nor `manage-livechat-sla` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
* **Invalid Inquiry:** This occurs when the inquiry is invalid.

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

{% tab title="Invalid Inquiry" %}
```
{
    "success": false,
    "error": "error-invalid-inquiry"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 5.0.0   | Added       |
