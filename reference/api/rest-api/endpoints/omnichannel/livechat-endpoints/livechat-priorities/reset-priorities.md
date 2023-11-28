# Reset Priorities

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

This endpoint resets all priorities back to default.

{% hint style="info" %}
You are required to have the `manage-livechat-priorities` permission.
{% endhint %}

<table><thead><tr><th width="163">HTTP Method</th><th width="362">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>api/v1/livechat/priorities.reset</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request POST 'http://localhost:3000/api/v1/livechat/priorities.reset' \
--header 'X-Auth-Token: sMmROZpdpCTbY43XwPT_bCsWJc-VW7v_e2urWhUM766' \
--header 'X-User-Id: rYhzFRd2QZjNwAAXX'
```
{% endcode %}

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
* **No Permission**: This occurs when the authenticated user doesn't have `manage-livechat-priorities` permission.

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
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| `6.0.0` | Added       |
