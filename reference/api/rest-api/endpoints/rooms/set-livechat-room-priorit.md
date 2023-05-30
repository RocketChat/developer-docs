# Set Livechat room Priority

Set the priority of a Live Chat room.

<figure><img src="../../../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
You are required to have the `view-l-room` permission.
{% endhint %}

<table><thead><tr><th width="356.3333333333333">URL</th><th>Requires Auth</th><th>HTTP Method</th></tr></thead><tbody><tr><td><code>api/v1/livechat/room/:rid/priority</code></td><td><code>YES</code></td><td><code>POST</code></td></tr></tbody></table>

## Headers

<table><thead><tr><th width="179">Argument</th><th width="169">Example</th><th width="143">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>X-User-Id</code></td><td><code>myuser-name</code></td><td>Required</td><td>The authenticated ouser ID.</td></tr><tr><td><code>X-Auth-Token</code></td><td><code>myauth-token</code></td><td>Required</td><td>Auth token.</td></tr></tbody></table>

## Path Parameters

<table><thead><tr><th width="152">Argument</th><th width="277">Example</th><th width="149">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>rid</code></td><td><code>tcbbSmWSLR5uo5PBW</code></td><td>Required</td><td>The Id of the Live Chat room.</td></tr></tbody></table>

## Payload

<table><thead><tr><th width="169">Argument</th><th width="215">Example</th><th width="158">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>priorityId</code></td><td><code>64007cc2fa0ed7dd905092e6</code></td><td>Required</td><td>The Id of the priority to set.</td></tr></tbody></table>

## Example Call

```powershell
curl --location 'http://localhost:3000/api/v1/livechat/room/tcbbSmWSLR5uo5PBW/priority' \
--header 'X-Auth-Token: sMmROZpdpCTbY43XwPT_bCsWJc-VW7v_e2urWhUM766' \
--header 'X-User-Id: rYhzFRd2QZjNwAAXX' \
--header 'Content-Type: application/json' \
--data '{
    "priorityId": "64007cc2fa0ed7dd905092e6"
}'
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
* **No Permission**: This occurs when the authenticated user doesn't have `view-l-room` permission.
* **Invalid Parameter**: Gets returned when no priority Id is sent in the body.
* **Invalid priority**: This error gets returned when no Priority is found with the Id provided.

{% tabs %}
{% tab title=" Authorization" %}
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
    "error": "error-not-authorized"
}
```
{% endtab %}

{% tab title="Unable to Update" %}
```json
{
    "success": false,
    "error": "must have required property 'priorityId' [invalid-params]",
    "errorType": "invalid-params"
}
```
{% endtab %}

{% tab title="Invalid Priority" %}
```json
{
    "success": false,
    "error": "error-invalid-priority"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 6.0.0   | Added       |
