# Get List of Livechat Rooms

Retrieves a list of Livechat rooms.

<table><thead><tr><th width="163">HTTP Method</th><th width="338">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/rooms</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

It supports the [#pagination](../../../../#pagination "mention") parameters, alongside the field parameter for [#query-and-fields](../../../../#query-and-fields "mention"). Additional optional query parameters are as follows:

<table><thead><tr><th width="201.33333333333331">Key</th><th width="247">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>agents</code></td><td><code>['b32h3b2hhwb25d']</code></td><td>A list of agents, can be a list of ids or usernames</td></tr><tr><td><code>departmentId</code></td><td><code>AkzpHAvZpdnuchw2a</code></td><td>The department's id</td></tr><tr><td><code>open</code></td><td><code>true</code></td><td>If it should filter by open/closed rooms</td></tr><tr><td><code>createdAt</code></td><td><code>{"start": "2018-01-26T00:11:22.345Z", "end": "2018-01-26T00:11:22.345Z"}</code></td><td>An object representing when the room was created(Can also be filtered only with <code>start</code> or <code>end</code>)</td></tr><tr><td><code>closedAt</code></td><td><code>{"start": "2018-01-26T00:11:22.345Z", "end": "2018-01-26T00:11:22.345Z"}</code></td><td>An object representing when the room was closed(Can also be filtered only with <code>start</code> or <code>end</code>)</td></tr><tr><td><code>tags</code></td><td><code>['rocket', 'chat']</code></td><td>A list of tags</td></tr><tr><td><code>customFields</code></td><td><code>{"docId": "aobEdbYhXfu5hkeqG"}</code></td><td>An object with custom fields to be filtered(previously created and populated at custom fields endpoints)</td></tr><tr><td><code>roomName</code></td><td><code>room name</code></td><td>The room's name</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/livechat/rooms?agents[]=agent1&agents[]=agent2&departamentId=123&open=true&createdAt={"start": "2018-01-26T00:11:22.345Z", "end": "2018-01-26T00:11:22.345Z"}&closedAt={"start": "2018-01-26T00:11:22.345Z", "end": "2018-01-26T00:11:22.345Z"}&tags[]=rocket&customFields={"docId": "031041"}&count=3&offset=1&sort={"_updatedAt": 1}&fields={"msgs": 1}&roomName=test
```
{% endcode %}

## Example Response

```json
{
    "rooms": [
        {
            "_id": "9dQMveZhqxiDgCM3B",
            "msgs": 1,
            "usersCount": 1,
            "lm": "2019-08-09T20:18:02.350Z",
            "fname": "Marcos Defendi",
            "t": "l",
            "ts": "2019-08-09T20:18:02.108Z",
            "v": {
                "_id": "xh45w4y7oPW5SiMJu",
                "username": "guest-4",
                "token": "xn5hdkyptei11m07f3me",
                "status": "online"
            },
            "servedBy": {
                "_id": "3kyWm8PsmwhC7xgwg",
                "username": "marcos",
                "ts": "2019-08-09T20:18:02.109Z"
            },
            "cl": false,
            "open": true,
            "waitingResponse": true,
            "departmentId": "xnmXQmytuvxp2TuSC",
            "_updatedAt": "2019-08-09T20:19:34.856Z",
            "lastMessage": {
                "_id": "TBEz7zSCBaKsfyrzc",
                "rid": "9dQMveZhqxiDgCM3B",
                "msg": "Hello",
                "token": "xn5hdkyptei11m07f3me",
                "alias": "Marcos Defendi",
                "ts": "2019-08-09T20:18:02.350Z",
                "u": {
                    "_id": "xh45w4y7oPW5SiMJu",
                    "username": "guest-4",
                    "name": "Marcos Defendi"
                },
                "_updatedAt": "2019-08-09T20:18:02.383Z",
                "mentions": [],
                "channels": [],
                "newRoom": false,
                "showConnecting": false
            },
            "metrics": {
                "v": {
                    "lq": "2019-08-09T20:18:02.350Z"
                }
            },
            "livechatData": {
                "docId": "0310584343112"
            },
            "tags": [
                "rocket",
                "chat"
            ],
            "name": "Marcos Defendi"
        }
    ],
    "count": 1,
    "offset": 1,
    "total": 7,
    "success": true
}
```

## Change Log

| Version | Description                               |
| ------- | ----------------------------------------- |
| 2.4.0   | Added support to the parameter `roomName` |
| 2.0.0   | Added                                     |
