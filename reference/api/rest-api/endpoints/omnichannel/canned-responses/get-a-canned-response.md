# Get a Canned Response

<figure><img src="../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Get a specific [canned response](https://docs.rocket.chat/use-rocket.chat/omnichannel/canned-responses).

<table><thead><tr><th width="163">HTTP Method</th><th width="332">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/canned-responses/:_id</code></td><td><a href="../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `view-canned-responses`
{% endhint %}

## Path Variables

<table><thead><tr><th width="212.33333333333331">Key</th><th width="238">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>_id</code><mark style="color:red;"><code>*</code></mark></td><td><code>EwmbZ9nLSx7kFamYB</code></td><td>The canned response's ID.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request DELETE 'http://localhost:3000/api/v1/canned-responses/EwmbZ9nLSx7kFamYB' \
--header 'X-User-Id: 2tTEqR7ZNMJ4HGGNa' \
--header 'X-Auth-Token: A6PF2Qa-w-gl1BvJ11jYiSMt6Z_G'
```
{% endcode %}

## Example Result

### Success

```json
{
  "cannedResponse": {
    "_id": "EwmbZ9nLSx7kFamYB",
    "shortcut": "user",
    "text": "Meu 32423423423423423",
    "scope": "user",
    "userId": "9L3wuBXKpbAWdfgx8",
    "createdBy": {
      "_id": "9L3wuBXKpbAWdfgx8",
      "username": "rafael.ferreira"
    },
    "_createdAt": "2021-05-26T18:59:17.929Z",
    "_updatedAt": "2021-05-26T18:59:17.929Z"
  },
  "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **No Permission**: Occurs when the authenticated user doesn't have the  `view-canned-responses` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).&#x20;

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
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 1.0.0   | Added       |
