# Search a visitors chat

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `api/v1/livechat/visitors.searchChats/room/:roomId/visitor/:visitorId` | `YES` | `GET` |

## Headers

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `X-User-Id` | `myuser-name` | Required | Your username hash \(returned after you log in through the API\) |
| `X-Auth-Token` | `myauth-token` | Required | Your token \(returned after you log in through the API\) |

## URL Parameters

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `roomId` | `hhMKhHnnbY79mGs9K` | Required | Livechat room id |
| `visitorId` | `QyBAKC5Wc8tcv6cco` | Required | Livechat visitor id |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/livechat/visitors.searchChats/room/:roomId/visitor/:visitorId\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript
{
    "history": [
        {
            "_id": "hhMKhHnnbY79mGs9K",
            "msgs": 2,
            "fname": "Maria",
            "ts": "2021-07-22T17:17:04.216Z",
            "v": {
                "_id": "QyBAKC5Wc8tcv6cco",
                "username": "guest-537",
                "token": "8s7e9ony6ctl27e1qf8kue",
                "status": "online",
                "lastMessageTs": "2021-07-22T17:17:04.937Z"
            }
        }
    ],
    "count": 1,
    "offset": 0,
    "total": 1,
    "success": true
}
```

