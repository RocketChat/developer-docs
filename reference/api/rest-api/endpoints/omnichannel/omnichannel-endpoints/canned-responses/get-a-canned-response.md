# Get a Canned Response

<figure><img src="../../../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

Get a [canned response](https://docs.rocket.chat/use-rocket.chat/omnichannel/canned-responses).

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
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/canned-responses/EwmbZ9nLSx7kFamYB
```

## Example Result

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

## Change Log

| Version | Description |
| ------- | ----------- |
| 1.0.0   | Added       |
