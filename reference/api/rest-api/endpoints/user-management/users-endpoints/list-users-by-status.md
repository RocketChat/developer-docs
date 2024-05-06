# List users by Status

Returns a list of filtered users based on activation status, first-time log-in, and type of users to be returned. It requires the `View Direct Messages`and `View Outside Room` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).

<table><thead><tr><th width="163">HTTP Method</th><th width="311">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>api/v1/users.listByStatus</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

This endpoint supports the optional [#pagination](../../../#pagination "mention") parameters.

<table><thead><tr><th>Key</th><th width="220.33333333333331">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>status</code></td><td><code>active</code></td><td>Filter users based on their activation status. It can either  be <code>active</code> or <code>deactivated</code></td></tr><tr><td><code>hasLoggedIn</code></td><td><code>true</code></td><td>Filter the users who have logged into their accounts for the first time.</td></tr><tr><td><code>type</code></td><td><code>user</code></td><td>Filter the type of users to be returned. For example, 'bot', 'user', 'app', etc.</td></tr><tr><td><code>roles[]</code></td><td><code>bot</code></td><td>Filter the users returned based on a list of roles.</td></tr><tr><td><code>searchTerm</code></td><td><code>test</code></td><td>Filter the list of users returned based on a search term</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/users.listByStatus
```

## Example Response&#x20;

```json
{
    "users": [
        {
            "_id": "W7MRNgkYLXKKAGNvW",
            "username": "agent1",
            "emails": [
                {
                    "address": "agent1@agent.com",
                    "verified": false
                }
            ],
            "type": "user",
            "roles": [
                "user",
                "livechat-agent"
            ],
            "status": "offline",
            "active": true,
            "name": "Agent 1",
            "lastLogin": "2024-04-24T17:47:50.485Z"
        },
        {
            "_id": "Tf44Q5AaYDehtJLzA",
            "username": "agent2",
            "emails": [
                {
                    "address": "agent2@agent.com",
                    "verified": false
                }
            ],
            "type": "user",
            "roles": [
                "user",
                "livechat-agent"
            ],
            "status": "offline",
            "active": true,
            "name": "Agent 2",
            "lastLogin": "2024-04-29T16:38:56.809Z"
        },
        {
            "_id": "JwATAtGzrzHYHCXFy",
            "username": "agent3",
            "emails": [
                {
                    "address": "agent3@agent.com",
                    "verified": false
                }
            ],
            "type": "user",
            "roles": [
                "user",
                "livechat-agent"
            ],
            "status": "online",
            "active": true,
            "name": "Agent3",
            "lastLogin": "2024-04-30T16:59:21.879Z"
        },
       
        {
            "_id": "u6C62WdHKNk5X8Rzr",
            "username": "guy",
            "emails": [
                {
                    "address": "guy@guy.com",
                    "verified": false
                }
            ],
            "type": "user",
            "roles": [
                "user"
            ],
            "status": "offline",
            "active": true,
            "name": "guy"
        },
	{
            "_id": "rocket.cat",
            "name": "Rocket.Cat",
            "username": "rocket.cat",
            "status": "online",
            "active": true,
            "type": "bot",
            "roles": [
                "bot"
            ],
            "avatarETag": "MEhPLkenJqs3jTJP5"
        }
    ],
    "count": 5,
    "offset": 0,
    "total": 5,
    "success": true
}
```

## Change Log

<table><thead><tr><th width="329">Version</th><th>Description</th></tr></thead><tbody><tr><td>6.8.0</td><td>Added</td></tr></tbody></table>
