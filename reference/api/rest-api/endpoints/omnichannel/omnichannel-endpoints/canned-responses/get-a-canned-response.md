# Get a Canned Response

<figure><img src="../../../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

Get a [canned response](https://docs.rocket.chat/use-rocket.chat/omnichannel/canned-responses).

| URL                             | Requires Auth | HTTP Method |
| ------------------------------- | ------------- | ----------- |
| `/api/v1/canned-responses/:_id` | `yes`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                 |
| -------------- | -------------- | -------- | --------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | The authenticated  user ID. |
| `X-Auth-Token` | `myauth-token` | Required | Auth token.                 |

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
