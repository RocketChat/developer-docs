# Get User's Info

Retrieves information about a user.

<table><thead><tr><th width="163">HTTP Method</th><th width="311">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/users.info</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

<table><thead><tr><th>Key</th><th width="220.33333333333331">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>userId</code><mark style="color:red;"><code>*</code></mark> or <code>username</code><mark style="color:red;"><code>*</code></mark></td><td><code>BsNr28znDkG8aeo7W</code></td><td>The ID or username of the user.</td></tr></tbody></table>

The result is only limited to what the callee has access to view. It supports the field parameter for [#query-and-fields](../../../#query-and-fields "mention") with the `userRooms` field, that returns the rooms that the user is part of. The `rooms` field returns the `unread` property and this field is variable, based on the setting `Unread_Count` (`Admin Panel` => `General` => `Unread_Count`), this setting provides the ability to choose between options to count the unread messages.

## Other Users Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/users.info?userId=BsNr28znDkG8aeo7W
```

## Example Response Regular User Callee

```json
{
    "user": {
        "_id": "5fRTXMt7DMJbpPJfh",
        "createdAt": "2023-07-10T16:44:58.548Z",
        "services": {
            "password": true,
            "email2fa": {
                "enabled": true,
                "changedAt": "2023-07-10T16:44:58.546Z"
            },
            "resume": {
                "loginTokens": [
                    {
                        "when": "2023-10-05T18:55:02.996Z",
                        "hashedToken": "..."
                    },
                    {
                        "when": "2023-10-05T19:09:30.415Z",
                        "hashedToken": "....."
                    },
                    {
                        "when": "2023-10-10T23:40:46.098Z",
                        "hashedToken": "...."
                    }
                ]
            }
        },
        "username": "test.john",
        "emails": [
            {
                "address": "test.john@test.com",
                "verified": true
            }
        ],
        "type": "user",
        "status": "offline",
        "active": true,
        "roles": [
            "user",
            "admin"
        ],
        "name": "Test John",
        "requirePasswordChange": false,
        "lastLogin": "2023-10-10T23:40:46.093Z",
        "statusConnection": "offline",
        "utcOffset": 1,
        "statusText": "",
        "avatarETag": "GFoEi6wv3uAxnzDcD",
        "nickname": "tesuser2",
        "canViewAllInfo": true
    },
    "success": true
}
```

## Example Response Admin Callee that requests user's rooms

{% code overflow="wrap" %}
```powershell
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/users.info?userId=BsNr28znDkG8aeo7W&fields={"userRooms": 1}
```
{% endcode %}

```json
{
    "user": {
        "_id": "5fRTXMt7DMJbpPJfh",
        "createdAt": "2023-07-10T16:44:58.548Z",
        "services": {
            "password": true,
            "email2fa": {
                "enabled": true,
                "changedAt": "2023-07-10T16:44:58.546Z"
            },
            "resume": {
                "loginTokens": [
                    {
                        "when": "2023-10-05T18:55:02.996Z",
                        "hashedToken": "..."
                    },
                    {
                        "when": "2023-10-05T19:09:30.415Z",
                        "hashedToken": "...."
                    },
                    {
                        "when": "2023-10-10T23:40:46.098Z",
                        "hashedToken": "...."
                    }
                ]
            }
        },
        "username": "test.john",
        "emails": [
            {
                "address": "test.john@test.com",
                "verified": true
            }
        ],
        "type": "user",
        "status": "offline",
        "active": true,
        "roles": [
            "user",
            "admin"
        ],
        "name": "Test John",
        "requirePasswordChange": false,
        "lastLogin": "2023-10-10T23:40:46.093Z",
        "statusConnection": "offline",
        "utcOffset": 1,
        "statusText": "",
        "avatarETag": "GFoEi6wv3uAxnzDcD",
        "nickname": "tesuser2",
        "canViewAllInfo": true,
        "rooms": [
            {
                "_id": "651667dda2f73c7460e18cce",
                "unread": 1,
                "rid": "JKa7R9zu2DinBhBN9",
                "name": "Livestream",
                "t": "c"
            },
            {
                "_id": "64ac358a79f5c6e276cfe718",
                "unread": 0,
                "rid": "GENERAL",
                "name": "general",
                "t": "c"
            },
            {
                "_id": "64aca0e5aa5ad4273bfbfdb8",
                "unread": 0,
                "rid": "6GFJ3tbmHiyHbahmC",
                "name": "test-audit",
                "t": "c"
            },
            {
                "_id": "64adb09baa5ad4273bfc0cc0",
                "unread": 0,
                "rid": "64adb09baa5ad4273bfc0cbf",
                "name": "test-room",
                "t": "c",
                "roles": [
                    "owner"
                ]
            },
            {
                "_id": "64fd791c2c26843a68c1f7e5",
                "unread": 0,
                "rid": "siyr2oWQJBjQjhLwr",
                "name": "try",
                "t": "c",
                "roles": []
            },
            {
                "_id": "g5xHGWAGLA7vZXwW8",
                "rid": "5fRTXMt7DMJbpPJfhrbAXPnMktTFbNpwtJ",
                "name": "roxie",
                "t": "d",
                "unread": 2
            },
            {
                "_id": "64ef8a982c26843a68c1f7ae",
                "unread": 0,
                "rid": "WDuJLFkjwk6L7LdFC",
                "name": "new",
                "t": "p",
                "roles": [
                    "leader"
                ]
            }
        ]
    },
    "success": true
}
```

## Change Log

<table><thead><tr><th width="342">Version</th><th>Description</th></tr></thead><tbody><tr><td>3.4.0</td><td>Added <code>unread</code> property inside <code>rooms</code> object</td></tr><tr><td>0.70.0</td><td>Added <code>rooms</code> property to response if the user request it and has the <code>view-other-user-channels</code> permission</td></tr><tr><td>0.49.0</td><td>Updated to support <code>userId</code> or <code>username</code></td></tr><tr><td>0.48.0</td><td>Renamed to <code>users.info</code></td></tr><tr><td>0.35.0</td><td>Added as <code>user.info</code></td></tr></tbody></table>
