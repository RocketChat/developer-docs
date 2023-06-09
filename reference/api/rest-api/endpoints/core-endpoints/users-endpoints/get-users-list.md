# Get Users List

Gets all of the users in the system and their information, the result is only limited to what the callee has access to view. It supports the [Offset, Count, and Sort Query Parameters](broken-reference) along with [Query and Fields Query Parameter](broken-reference).

| URL                  | Requires Auth | HTTP Method |
| -------------------- | ------------- | ----------- |
| `/api/v1/users.list` | `yes`         | `GET`       |

## Query Parameters

| Argument | Example                                            | Required | Description                                                   |
| -------- | -------------------------------------------------- | -------- | ------------------------------------------------------------- |
| `fields` | `{ name: 1, emails: 0 }`                           | Optional | Field include hash (value of `1` to include, `0` to exclude). |
| `query`  | `{ active: true, type: { $in: ['user', 'bot'] } }` | Optional | Query filter hash.                                            |

## Other Users Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/users.list
```

## Example Result Regular User Callee

```javascript
{
  "users": [
    {
      "_id": "nSYqWzZ4GsKTX4dyK",
      "type": "user",
      "status": "offline",
      "active": true,
      "name": "Example User",
      "utcOffset": 0,
      "username": "example"
    },
    {
      ...
    }
  ],
  "count": 10,
  "offset": 0,
  "total": 10,
  "success": true
}
```

## Example Result Admin Callee

```javascript
{
    "users": [
        {
            "_id": "Bm9YcfBCrwSTSGof7",
            "username": "botkit.user",
            "emails": [
                {
                    "address": "botkit@user.cm",
                    "verified": false
                }
            ],
            "status": "offline",
            "active": true,
            "roles": [
                "bot"
            ],
            "name": "Botkit User",
            "nameInsensitive": "botkit user"
        },
        
        {
            "_id": "Fdh2KgsB7dtwbYrNw",
            "username": "john.m",
            "emails": [
                {
                    "address": "john@m.com",
                    "verified": true
                }
            ],
            "status": "offline",
            "active": true,
            "roles": [
                "user"
            ],
            "name": "John M",
            "nameInsensitive": "john m"
        },
        {...},
        {
            "_id": "jowYXPgJoKaoxzz4q",
            "username": "user.one",
            "emails": [
                {
                    "address": "remego8086@d3ff.com",
                    "verified": false
                }
            ],
            "status": "offline",
            "active": true,
            "roles": [
                "livechat-manager",
                "livechat-agent"
            ],
            "name": "User One",
            "nameInsensitive": "user one"
        }
    ],
    "count": 11,
    "offset": 0,
    "total": 11,
    "success": true
}
```

## Change Log

| Version | Description                                  |
| ------- | -------------------------------------------- |
| 0.49.0  | Count and offset query parameters supported. |
| 0.35.0  | Added                                        |
