# Search Visitors by term

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `api/v1/livechat/visitors.search` | `YES` | `GET` |

## Headers

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `X-User-Id` | `myuser-name` | Required | Your username hash \(returned after you log in through the API\) |
| `X-Auth-Token` | `myauth-token` | Required | Your token \(returned after you log in through the API\) |

## Parameters

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `term` | `Maria` | Optional | Search Term |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/api/v1/livechat/visitors.search\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript
{
    "visitors": [
        {
            "_id": "QyBAKC5Wc8tcv6cco",
            "username": "guest-537",
            "name": "Maria",
            "visitorEmails": [
                {
                    "address": "Maria@gmail.com"
                }
            ],
            "lastChat": {
                "_id": "hhMKhHnnbY79mGs9K",
                "ts": "2021-07-22T17:17:04.234Z"
            }
        },
        {
            "_id": "SuE3sQA277bqpLkte",
            "username": "guest-415",
            "name": "Maria Carvalho",
            "visitorEmails": [
                {
                    "address": "maria.carvalho@mail.com"
                }
            ],
            "livechatData": {
                "company": "Rocket.Chat",
                "Promotions": "@"
            },
            "lastChat": {
                "_id": "ksXhSRfjDnvb5vu4Q",
                "ts": "2021-06-29T02:57:47.339Z"
            }
        },
        {
            "_id": "uRv3XkeTRWmcZK86M",
            "username": "5511945770489",
            "phone": [
                {
                    "phoneNumber": "whatsapp:+5511945770489"
                }
            ],
            "name": "Maria"
        }
    ],
    "count": 3,
    "offset": 0,
    "total": 3,
    "success": true
}
```

