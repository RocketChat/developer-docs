# Remove Livechat room Priority

Remove the priority set to a Live Chat room.

<figure><img src="../../../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
You are required to have the `view-l-room` permission.
{% endhint %}

<table><thead><tr><th width="356.3333333333333">URL</th><th>Requires Auth</th><th>HTTP Method</th></tr></thead><tbody><tr><td><code>api/v1/livechat/room/:rid/priority</code></td><td><code>YES</code></td><td><code>DELETE</code></td></tr></tbody></table>

## Headers

<table><thead><tr><th width="179">Argument</th><th width="169">Example</th><th width="143">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>X-User-Id</code></td><td><code>myuser-name</code></td><td>Required</td><td>The authenticated ouser ID.</td></tr><tr><td><code>X-Auth-Token</code></td><td><code>myauth-token</code></td><td>Required</td><td>Auth token.</td></tr></tbody></table>

## Path Parameters

<table><thead><tr><th width="152">Argument</th><th width="277">Example</th><th width="149">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>rid</code></td><td><code>tcbbSmWSLR5uo5PBW</code></td><td>Required</td><td>The Id of the Live Chat room.</td></tr></tbody></table>

## Example Call

```powershell
curl --location --request DELETE 'http://localhost:3000/api/v1/livechat/room/tcbbSmWSLR5uo5PBW/priority' \
--header 'X-Auth-Token: sMmROZpdpCTbY43XwPT_bCsWJc-VW7v_e2urWhUM766' \
--header 'X-User-Id: rYhzFRd2QZjNwAAXX'
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
* **Error room**: This error gets returned when no Room is found with the Id provided.

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

{% tab title="Error room" %}
```json
{
    "success": false,
    "error": "error-room-does-not-exist"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 6.0.0   | Added       |
