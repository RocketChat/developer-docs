# Remove Canned Response

<figure><img src="../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Remove a [canned response](https://docs.rocket.chat/use-rocket.chat/omnichannel/canned-responses).

<table><thead><tr><th width="163">HTTP Method</th><th width="332">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>DELETE</code></td><td><code>/api/v1/canned-responses</code></td><td><a href="../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `remove-canned-responses`
{% endhint %}

## Body Parameters

<table><thead><tr><th width="212.33333333333331">Key</th><th width="238">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>_id</code><mark style="color:red;"><code>*</code></mark></td><td><code>EwmbZ9nLSx7kFamYB</code></td><td>The canned response's ID.</td></tr></tbody></table>

## Example Call

```powershell
curl --location --request DELETE 'http://localhost:3000/api/v1/canned-responses' \
--header 'X-User-Id: 2tTEqR7ZNMJ4HGGNa' \
--header 'X-Auth-Token: A6PF2Qa-wXunBXi3j77OBY-T-gl1BvJ11jYiSMt6Z_G' \
--data '{
            "_id": "64700874a8c3a3ba32d0fb1c"
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
* **No Permission**: Occurs when the authenticated user doesn't have the  `logout-device-management` permission.
* **Canned Response not found:**  Occurs when the `_id` of the canned response does not exist.

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

{% tab title="Canned Response not found" %}
```json
{
    "success": false,
    "error": "Canned Response not found [error-canned-response-not-found]",
    "errorType": "error-canned-response-not-found",
    "details": {
        "method": "removeCannedResponse"
    }
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 1.0.0   | Added       |
