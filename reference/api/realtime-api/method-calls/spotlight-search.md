# Spotlight (search)

Search for rooms or users.

| Name        | Requires Auth | Permission | Setting |
| ----------- | ------------- | ---------- | ------- |
| `spotlight` | Yes           |            |         |

## Payload Parameters

| Argument       | Example                             | Required | Description                                                               |
| -------------- | ----------------------------------- | -------- | ------------------------------------------------------------------------- |
| `searchString` | `test`                              | Required | The term to be searched for.                                              |
| `exclude`      | `test.rc`                           | Optional | Any items to exclude from the results (e.g. users you already know about) |
| `options`      | `{ "users": true, "rooms": false }` | Required | What kinds of fields to search for                                        |

## Example Call

```
{
    "msg": "method",
    "method": "spotlight",
    "params": ["test", ["testrc"], {
        "users": true,
        "rooms": false
    }],
    "id": "74290"
}
```

## Example Response

```
{
    "msg": "result",
    "id": "74290",
    "result": {
        "users": [
            {
                "_id": "ZoJM4tvohREwJbtAh",
                "username": "testrc",
                "status": "offline",
                "name": "TestRc",
                "outside": true
            }
        ],
        "rooms": []
    }
}

```
