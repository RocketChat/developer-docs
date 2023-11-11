# Remove Livechat Room Priority

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Remove the priority set to a Livechat room.

{% hint style="info" %}
You are required to have the `view-l-room` permission.
{% endhint %}

<table><thead><tr><th width="163">HTTP Method</th><th width="338">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>DELETE</code></td><td><code>/api/v1/livechat/room/:rid/priority</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Path Variables

<table><thead><tr><th width="152">Key</th><th width="277">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>rid</code><mark style="color:red;"><code>*</code></mark></td><td><code>tcbbSmWSLR5uo5PBW</code></td><td>The room ID.</td></tr></tbody></table>

## Example Call

```powershell
curl --location --request DELETE 'http://localhost:3000/api/v1/livechat/room/tcbbSmWSLR5uo5PBW/priority' \
--header 'X-Auth-Token: sMmROZpdpCTbY43XwPT_bCsWJc-VW7v_e2urWhUM766' \
--header 'X-User-Id: rYhzFRd2QZjNwAAXX'
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
