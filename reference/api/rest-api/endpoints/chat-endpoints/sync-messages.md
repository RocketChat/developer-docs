# Sync Messages

It supports the [Query, Fields](../other-important-endpoints/query-and-fields-info.md#query-example) and [sort](../other-important-endpoints/offset-and-count-and-sort-info.md).

| URL                         | Requires Auth | HTTP Method |
| --------------------------- | ------------- | ----------- |
| `/api/v1/chat.syncMessages` | `yes`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Query Parameters

| Argument     | Example                    | Required | Description        |
| ------------ | -------------------------- | -------- | ------------------ |
| `roomId`     | `5qW6ssMFyzWjJev69`        | Required | Room ID            |
| `lastUpdate` | `2019-04-16T18:30:46.669Z` | Required | Date as ISO string |

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/chat.syncMessages?roomId=5qW6ssMFyzWjJev69&lastUpdate=2019-04-16T18:30:46.669Z
```

## Example Result

```javascript
{
    "result": {
        "updated": [
            {
                "_id": "ak3WdaLbf4P7ZW3wQ",
                "rid": "5qW6ssMFyzWjJev69",
                "u": {
                    "_id": "FWfHnJmcudrCagGDX",
                    "username": "555192857993",
                    "name": "555192857993"
                },
                "msg": "teste",
                "ts": "2021-09-24T19:19:47.911Z",
                "_updatedAt": "2021-09-24T19:19:48.048Z",
                "alias": "mauricio pretto",
                "token": "do554ryecscmfrrxyxpvm",
                "unread": true,
                "urls": [],
                "mentions": [],
                "channels": [],
                "md": [
                    {
                        "type": "PARAGRAPH",
                        "value": [
                            {
                                "type": "PLAIN_TEXT",
                                "value": "teste"
                            }
                        ]
                    }
                ]
            },
            {
                "_id": "2ttrNPABcCKbsbEtB",
                "t": "livechat-started",
                "msg": "",
                "groupable": false,
                "ts": "2021-09-24T19:19:46.523Z",
                "u": {
                    "_id": "FWfHnJmcudrCagGDX",
                    "username": "555192857993",
                    "name": "555192857993"
                },
                "rid": "5qW6ssMFyzWjJev69",
                "unread": true,
                "_updatedAt": "2021-09-24T19:19:46.691Z",
                "urls": [],
                "mentions": [],
                "channels": []
            }
        ],
        "deleted": []
    },
    "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 1.0.0   | Added       |
