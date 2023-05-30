---
description: Retrieves all custom emojis
---

# List all custom emojis

| URL                        | Requires Auth | HTTP Method |
| -------------------------- | ------------- | ----------- |
| `/api/v1/emoji-custom.all` | `yes`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/emoji-custom.all
```

## Example Result

```javascript
{
    "emojis": [
        {
            "_id": "XmLyhaRbySkjhA2cL",
            "name": "fon",
            "aliases": [],
            "extension": "jpeg",
            "_updatedAt": "2021-07-14T14:59:06.268Z"
        },
        {
            "_id": "SnXhYeKxrgEKfgiBp",
            "name": "penguin_moji",
            "aliases": [
                "penguin"
            ],
            "extension": "jpeg",
            "_updatedAt": "2020-09-15T16:47:44.129Z"
        },
        {
            "_id": "mSyfgE8fs2YmDWXEQ",
            "name": "test",
            "aliases": [
                "asdfasdfa"
            ],
            "extension": "jpeg",
            "_updatedAt": "2021-03-02T02:41:00.181Z"
        }
    ],
    "count": 3,
    "offset": 0,
    "total": 3,
    "success": true
}
```
