# Create a Canned Response

<figure><img src="../../../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

Create a new [canned response](https://docs.rocket.chat/use-rocket.chat/omnichannel/canned-responses).

| URL                        | Requires Auth | HTTP Method |
| -------------------------- | ------------- | ----------- |
| `/api/v1/canned-responses` | `yes`         | `POST`      |

## Headers

| Argument       | Example        | Required | Description                 |
| -------------- | -------------- | -------- | --------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | The authenticated  user ID. |
| `X-Auth-Token` | `myauth-token` | Required | Auth token.                 |

## Payload

| Argument   | Example                            | Required | Description                          |
| ---------- | ---------------------------------- | -------- | ------------------------------------ |
| `shortcut` | `card-declined`                    | Required | The shortcut to the message snippet. |
| `text`     | `reasons for your cardmalfunction` | Required | The message snippet                  |
| `scope`    | `global`                           | Required | The scope of the canned response     |
| tags       | `card`                             | Optional | The tags for your canned response.   |

## Example payload

```javascript
{
    "shortcut": "my-new-canned",
    "text": "This is an example",
    "scope": "global",
    "tags": ["tag1", "tag2"]
}
```

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -X POST \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/canned-responses \
    -d '{    "shortcut": "my-new-canned", "text": "This is an example", "scope": "global", "tags": ["tag1", "tag2"] }'
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
