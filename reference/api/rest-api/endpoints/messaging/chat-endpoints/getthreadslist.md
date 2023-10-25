# List Threads

List threads in a room. It supports the [#pagination](../../../#pagination "mention") parameters, alongside the  [#query-and-fields](../../../#query-and-fields "mention") parameters.

| URL                           | Requires Auth | HTTP Method |
| ----------------------------- | ------------- | ----------- |
| `/api/v1/chat.getThreadsList` | `yes`         | `GET`       |

## Payload

| Argument | Example             | Required | Description         |
| -------- | ------------------- | -------- | ------------------- |
| `rid`    | `7aDSXtjMA3KPLxLjt` | Required | The id of the room. |

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type:application/json" \
     http://localhost:3000/api/v1/chat.getThreadsList?rid=GENERAL
```

## Example Result

```javascript
{
    "threads": [
        {
            "_id": "NZieMNQDEdMDmLLip",
            "rid": "6GFJ3tbmHiyHbahmC",
            "msg": "hola",
            "ts": "2023-10-05T20:30:51.052Z",
            "u": {
                "_id": "rbAXPnMktTFbNpwtJ",
                "username": "roxie",
                "name": "Funke Olasupo"
            },
            "_updatedAt": "2023-10-16T22:57:27.362Z",
            "urls": [],
            "mentions": [],
            "channels": [],
            "md": [
                {
                    "type": "PARAGRAPH",
                    "value": [
                        {
                            "type": "PLAIN_TEXT",
                            "value": "hola"
                        }
                    ]
                }
            ],
            "reactions": {
                ":smile:": {
                    "usernames": [
                        "test.funke"
                    ]
                }
            },
            "starred": [],
            "pinned": true,
            "pinnedAt": "2023-10-05T20:59:44.433Z",
            "pinnedBy": {
                "_id": "5fRTXMt7DMJbpPJfh",
                "username": "test.funke"
            },
            "replies": [
                "rbAXPnMktTFbNpwtJ"
            ],
            "tcount": 2,
            "tlm": "2023-10-16T22:57:27.158Z"
        }
    ],
    "count": 1,
    "offset": 0,
    "total": 1,
    "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 1.0.0   | Added       |
