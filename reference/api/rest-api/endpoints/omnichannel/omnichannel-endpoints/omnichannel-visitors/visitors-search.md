# Search Visitors by term

Search Omnichannel visitors using a term.

{% hint style="info" %}
You are required to have the `view-l-room` permission.
{% endhint %}

| URL                               | Requires Auth | HTTP Method |
| --------------------------------- | ------------- | ----------- |
| `api/v1/livechat/visitors.search` | `YES`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Parameters

| Argument | Example | Required | Description |
| -------- | ------- | -------- | ----------- |
| `term`   | `James` | Required | Search Term |

## Example Call

```bash
curl --location 'http://localhost:3000/api/v1/livechat/visitors.search?term=James' \
--header 'X-Auth-Token: EZmA1YMbEfghEPOmc03k0R9QiuVvKWjQClKVoF8x7LY' \
--header 'X-User-Id: rYhzFRd2QZjNwAAXX'
```

## Result

```javascript
{
    "visitors": [
        {
            "_id": "6410749f28384134ed600ce4",
            "username": "guest-14",
            "name": "James",
            "visitorEmails": [
                {
                    "address": "pilebe6631@kaudat.com"
                }
            ],
            "lastChat": {
                "_id": "eJ5ZzeT2XkLtcBkMM",
                "ts": "2023-03-14T13:21:02.239Z"
            }
        },
        {
            "_id": "63db8d4990fe6eda42ad429a",
            "username": "guest-3",
            "name": "James",
            "visitorEmails": [
                {
                    "address": "f.r@rocket.chat"
                }
            ],
            "lastChat": {
                "_id": "82htiMFZLCtvRFqZi",
                "ts": "2023-02-06T12:34:53.392Z"
            }
        }
    ],
    "count": 2,
    "offset": 0,
    "total": 2,
    "success": true
}
```
