# Search public rooms

<figure><img src="../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

Search for federated public rooms by the server name or room name.

| URL                                    | Requires Auth | HTTP Method |
| -------------------------------------- | ------------- | ----------- |
| `/api/v1/federation/searchPublicRooms` | `yes`         | `GET`       |

## Path Variables

| Argument     | Example                                                    | Required | Description                                                                         |
| ------------ | ---------------------------------------------------------- | -------- | ----------------------------------------------------------------------------------- |
| `serverName` | `matrix.org`                                               | Required | The server name.                                                                    |
| `roomName`   | `my public room name`                                      | Optional | The room name you want to search for in the server.                                 |
| `pageToken`  | `g6FtzRlCoXK+IUpmSlFNV0dlUkN4WFlRU2RXRDptYXRyaXgub3JnoWTD` | Optional | The page you want to retrieve, use it for pagination. Make sure to URL encode this. |
| `count`      | `50`                                                       | Optional | How many items do you want to get. Default `100`.                                   |

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/federation/searchPublicRooms?serverName=matrix.org
```

## Example Result

```javascript
{
    "rooms": [
        {
            "id": "!OGEhHVWSdvArJzumhm:matrix.org",
            "name": "Matrix HQ",
            "canJoin": true,
            "canonicalAlias": "#matrix:matrix.org",
            "joinedMembers": 44461,
            "topic": "The Official Matrix HQ - chat about Matrix here! | https://matrix.org | https://spec.matrix.org | To support Matrix.org development: https://patreon.com/matrixdotorg | Code of Conduct: https://matrix.org/legal/code-of-conduct/ | This is an English speaking room"
        }
    ],
    "count": 1,
    "total": 73080,
    "nextPageToken": "g6FtzZa3oXK+IUpkemFiTlVQUFh6bENKQWhFbDpmYWJyaWMucHVioWTD",
    "prevPageToken": "g6FtzYqIoXK+IWNOd2pkUXdWcFJNc0lNa1VweDptYXRyaXgub3JnoWTC",
    "success": true
}
```

<table><thead><tr><th>Version</th><th>Description</th><th data-hidden></th></tr></thead><tbody><tr><td>6.0.0</td><td>Added</td><td></td></tr></tbody></table>

