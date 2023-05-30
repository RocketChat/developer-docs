# Remove Canned Response

<figure><img src="../../../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

Remove a [canned response](https://docs.rocket.chat/use-rocket.chat/omnichannel/canned-responses).

| URL                        | Requires Auth | HTTP Method |
| -------------------------- | ------------- | ----------- |
| `/api/v1/canned-responses` | `yes`         | `DELETE`    |

## Payload

| Argument | Example             | Required | Description               |
| -------- | ------------------- | -------- | ------------------------- |
| `_id`    | `EwmbZ9nLSx7kFamYB` | Required | The canned response's id. |

## Example payload

```json
{
    "_id": "646c7350a8c3a3ba32d0e2e0"
}

```

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -X DELETE \
     http://localhost:3000/api/v1/canned-responses?
      -d '{"_id": "646c7350a8c3a3ba32d0e2e0}'
```

## Example Result

```javascript
{
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 1.0.0   | Added       |
