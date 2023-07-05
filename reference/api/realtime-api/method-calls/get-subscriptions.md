# Get Subscriptions

Returns a user's subscription collection.&#x20;



| Name                | Requires Auth | Permission | Setting |
| ------------------- | ------------- | ---------- | ------- |
| `subscriptions/get` | Yes           |            |         |

### Payload Parameters <a href="#payload-parameters" id="payload-parameters"></a>

| Argument | Example                   | Required | Description                                                                                                          |
| -------- | ------------------------- | -------- | -------------------------------------------------------------------------------------------------------------------- |
| `date`   | `{ "$date": 1480377601 }` | Optional | Filters the results to  contain the updated and removed subscriptions after the provided time. It accepts timestamp. |



## Example call to retrieve all settings

```javascript
{
    "msg": "method",
    "method": "subscriptions/get",
    "id": "4232",
    "params": []
}
```

### Response

```json
{
    "msg": "result",
    "id": "4232",
    "result": [
        {
            "_id": "64a37804730ef04d3db25571",
            "open": true,
            "alert": false,
            "unread": 0,
            "userMentions": 0,
            "groupMentions": 0,
            "ts": {
                "$date": 1688434691876
            },
            "rid": "64a37803730ef04d3db2556f",
            "name": "test-privadte-websockset",
            "fname": "test-privadte-websockset",
            "t": "p",
            "u": {
                "_id": "LFdhbcNHx5zsMA7T4",
                "username": "test.rc"
            },
            "ls": {
                "$date": 1688434691876
            },
            "_updatedAt": {
                "$date": 1688434692201
            },
            "roles": [
                "owner"
            ]
        },
        {
            "_id": "64a377ee730ef04d3db2556e",
            "open": true,
            "alert": false,
            "unread": 0,
            "userMentions": 0,
            "groupMentions": 0,
            "ts": {
                "$date": 1688434670589
            },
            "rid": "64a377ee730ef04d3db2556d",
            "name": "test-private-websocket",
            "fname": "test-private-websocket",
            "t": "p",
            "u": {
                "_id": "LFdhbcNHx5zsMA7T4",
                "username": "test.rc"
            },
            "ls": {
                "$date": 1688434670589
            },
            "_updatedAt": {
                "$date": 1688434670813
            },
            "roles": [
                "owner"
            ]
        },
        {
            "_id": "64a1f373376181965ab77f55",
            "open": true,
            "alert": false,
            "unread": 0,
            "userMentions": 0,
            "groupMentions": 0,
            "ts": {
                "$date": 1688335219412
            },
            "rid": "64a1f373376181965ab77f54",
            "name": "test-socket",
            "fname": "test-socket",
            "t": "c",
            "u": {
                "_id": "LFdhbcNHx5zsMA7T4",
                "username": "test.rc"
            },
            "ls": {
                "$date": 1688431340102
            },
            "_updatedAt": {
                "$date": 1688431340102
            },
            "roles": [
                "owner"
            ],
            "archived": false
        },
        {
            "_id": "CosNGF78DFEb5eRQe",
            "rid": "LFdhbcNHx5zsMA7T4ZoJM4tvohREwJbtAh",
            "u": {
                "_id": "LFdhbcNHx5zsMA7T4",
                "username": "test.rc"
            },
            "_updatedAt": {
                "$date": 1688513999557
            },
            "alert": false,
            "fname": "TestRc",
            "groupMentions": 0,
            "name": "testrc",
            "open": true,
            "t": "d",
            "unread": 0,
            "userMentions": 0
        }
    ]
}
```

## Example call to retrieve the updated and removed subscriptions since the provided date

```
{
    "msg": "method",
    "method": "subscriptions/get",
    "id": "4232",
    "params": [ { "$date": 1480377601 } ]
}
```

### Response

```javascript
{
    "msg": "result",
    "id": "4232",
    "result": {
        "update": [
            {
                "_id": "64a37804730ef04d3db25571",
                "open": true,
                "alert": false,
                "unread": 0,
                "userMentions": 0,
                "groupMentions": 0,
                "ts": {
                    "$date": 1688434691876
                },
                "rid": "64a37803730ef04d3db2556f",
                "name": "test-privadte-websockset",
                "fname": "test-privadte-websockset",
                "t": "p",
                "u": {
                    "_id": "LFdhbcNHx5zsMA7T4",
                    "username": "test.rc"
                },
                "ls": {
                    "$date": 1688434691876
                },
                "_updatedAt": {
                    "$date": 1688434692201
                },
                "roles": [
                    "owner"
                ]
            },
            {
                "_id": "64a377ee730ef04d3db2556e",
                "open": true,
                "alert": false,
                "unread": 0,
                "userMentions": 0,
                "groupMentions": 0,
                "ts": {
                    "$date": 1688434670589
                },
                "rid": "64a377ee730ef04d3db2556d",
                "name": "test-private-websocket",
                "fname": "test-private-websocket",
                "t": "p",
                "u": {
                    "_id": "LFdhbcNHx5zsMA7T4",
                    "username": "test.rc"
                },
                "ls": {
                    "$date": 1688434670589
                },
                "_updatedAt": {
                    "$date": 1688434670813
                },
                "roles": [
                    "owner"
                ]
            },
            {
                "_id": "64a1f373376181965ab77f55",
                "open": true,
                "alert": false,
                "unread": 0,
                "userMentions": 0,
                "groupMentions": 0,
                "ts": {
                    "$date": 1688335219412
                },
                "rid": "64a1f373376181965ab77f54",
                "name": "test-socket",
                "fname": "test-socket",
                "t": "c",
                "u": {
                    "_id": "LFdhbcNHx5zsMA7T4",
                    "username": "test.rc"
                },
                "ls": {
                    "$date": 1688431340102
                },
                "_updatedAt": {
                    "$date": 1688431340102
                },
                "roles": [
                    "owner"
                ],
                "archived": false
            },
            {
                "_id": "CosNGF78DFEb5eRQe",
                "rid": "LFdhbcNHx5zsMA7T4ZoJM4tvohREwJbtAh",
                "u": {
                    "_id": "LFdhbcNHx5zsMA7T4",
                    "username": "test.rc"
                },
                "_updatedAt": {
                    "$date": 1688513999557
                },
                "alert": false,
                "fname": "TestRc",
                "groupMentions": 0,
                "name": "testrc",
                "open": true,
                "t": "d",
                "unread": 0,
                "userMentions": 0
            }
        ],
        "remove": [
            {
                "_id": "64a1f540376181965ab77f5c",
                "_deletedAt": {
                    "$date": 1688349552878
                }
            },
            {
                "_id": "64a1f278376181965ab77f51",
                "_deletedAt": {
                    "$date": 1688351582328
                }
            }
        ]
    }
}
```
