# Get a Priority

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Get the details of a specific priority.

{% hint style="info" %}
You are required to have the `manage-livechat-priorities` or `view-l-room permission`.
{% endhint %}

<table><thead><tr><th width="163">HTTP Method</th><th width="362">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/priorities/:priorityId</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

## Path Variables

<table><thead><tr><th width="190.33333333333331">Key</th><th>Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>priorityId</code><mark style="color:red;"><code>*</code></mark></td><td><code>64007cc2fa0ed7dd905092e3</code></td><td>The priority ID.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location 'http://localhost:3000/api/v1/livechat/priorities/64007cc2fa0ed7dd905092e3' \
--header 'X-Auth-Token: sMmROZpdpCTbY43XwPT_bCsWJc-VW7v_e2urWhUM766' \
--header 'X-User-Id: rYhzFRd2QZjNwAAXX'
```
{% endcode %}

## Example Response

### Success

```json
{
    "_id": "64007cc2fa0ed7dd905092e3",
    "i18n": "Lowest",
    "sortItem": 5,
    "dirty": false,
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **No Permission**: This occurs when the authenticated user doesn't have `manage-livechat-priorities` or `view-l-room` permission.
* **Not Found**: This error gets returned when no Priority is found with the Id provided.

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
```
{
    "success": false,
    "error": "error-not-authorized"
}
```
{% endtab %}

{% tab title="Not Found" %}
```json
{
    "success": false,
    "error": "Priority with id :priorityId not found"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| `6.0.0` | Added       |
