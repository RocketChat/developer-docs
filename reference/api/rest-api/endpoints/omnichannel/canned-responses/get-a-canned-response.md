# Get a Canned Response

<figure><img src="../../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

Get a [canned response](https://docs.rocket.chat/use-rocket.chat/omnichannel/canned-responses).

{% hint style="info" %}
It requires only the `view-canned-responses` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).&#x20;
{% endhint %}

| URL                             | Requires Auth | HTTP Method |
| ------------------------------- | ------------- | ----------- |
| `/api/v1/canned-responses/:_id` | `yes`         | `GET`       |

## Headers

<table><thead><tr><th width="179">Argument</th><th width="169">Example</th><th width="136">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>X-User-Id</code></td><td><code>myuser-name</code></td><td>Required</td><td>The authenticated  user ID.</td></tr><tr><td><code>X-Auth-Token</code></td><td><code>myauth-token</code></td><td>Required</td><td>Auth token.</td></tr></tbody></table>

## Path Parameter

| Argument | Example           | Required | Description               |
| -------- | ----------------- | -------- | ------------------------- |
| `_id`    | EwmbZ9nLSx7kFamYB | Required | The canned response's id. |

## Example Call

```bash
curl --location --request DELETE 'http://localhost:3000/api/v1/canned-responses' \
--header 'X-User-Id: 2tTEqR7ZNMJ4HGGNa' \
--header 'X-Auth-Token: A6PF2Qa-wXunBXi3j77OBY-T-gl1BvJ11jYiSMt6Z_G' \
--data '{
            "_id": "64700874a8c3a3ba32d0fb1c"
}'
```

## Example Result

### Success

```javascript
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
