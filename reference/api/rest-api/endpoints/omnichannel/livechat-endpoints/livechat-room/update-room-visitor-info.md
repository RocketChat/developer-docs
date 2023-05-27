---
description: Updates room visitor's information
---

# Update Room Visitor Info

{% hint style="info" %}
You are required to have `the view-l-room` permission.
{% endhint %}

<table><thead><tr><th width="364.3333333333333">URL</th><th>Requires Auth</th><th>HTTP Method</th></tr></thead><tbody><tr><td><code>/api/v1/livechat/room.visitor</code></td><td><code>yes</code></td><td><code>PUT</code></td></tr></tbody></table>

## Payload

<table><thead><tr><th width="179">Argument</th><th>Example</th><th width="131">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>rid</code></td><td><code>XFzMqgn33DcsQkpJp</code></td><td>Required</td><td>The room <code>_id</code>.</td></tr><tr><td><code>newvisitorId</code></td><td><code>iNKE8a6k6cjbqWhWd</code></td><td>Required</td><td>The visitor's new <code>id</code>.</td></tr><tr><td><code>oldVisitorId</code></td><td><code>iNKE8a6k6cjbqWhWd</code></td><td>Required</td><td>The visitor's old <code>id</code>.</td></tr></tbody></table>

## Example payload

```json
{
    "rid": "tcbbSmWSLR5uo5PBW",
    "oldVisitorId": "6425bb86c29657e5b3ba26b2",
    "newVisitorId": "6425bb86c29657e5b3ba26b2"
}
```

## Example Call

```bash
curl --location --request PUT 'http://localhost:3000/api/v1/livechat/room.visitor' \
--header 'X-Auth-Token: 8kZl86mlaQW4tiHelu2GVrn1_DCu26kiLIoE2N3YAzs' \
--header 'X-User-Id: rYhzFRd2QZjNwAAXX' \
--header 'Content-Type: application/json' \
--data '{
    "rid": "tcbbSmWSLR5uo5PBW",
    "oldVisitorId": "6425bb86c29657e5b3ba26b2",
    "newVisitorId": "6425bb86c29657e5b3ba26b2"
}'
```

## Example Result

```json
{
    "room": {
        "_id": "tcbbSmWSLR5uo5PBW",
        "msgs": 5,
        "usersCount": 2,
        "lm": "2023-03-30T16:58:11.899Z",
        "fname": "Mende",
        "t": "l",
        "ts": "2023-03-30T16:40:48.026Z",
        "v": {
            "_id": "6425bb86c29657e5b3ba26b2",
            "username": "guest-16",
            "token": "8b15e7f76d3943646b9de8ca1e12aecb55297a321d29500e16143fa5bd6c622d",
            "status": "offline",
            "lastMessageTs": "2023-03-30T16:58:11.899Z"
        },
        "cl": false,
        "open": true,
        "source": {
            "type": "widget"
        },
        "queuedAt": "2023-03-30T16:40:48.026Z",
        "priorityWeight": 99,
        "estimatedWaitingTimeQueue": 9999999,
        "_updatedAt": "2023-05-02T14:47:45.855Z",
        "lastMessage": {
            "_id": "KLgpbsdZEgETahypp",
            "rid": "tcbbSmWSLR5uo5PBW",
            "msg": "Xup?",
            "token": "8b15e7f76d3943646b9de8ca1e12aecb55297a321d29500e16143fa5bd6c622d",
            "alias": "Mende",
            "ts": "2023-03-30T16:58:11.899Z",
            "u": {
                "_id": "6425bb86c29657e5b3ba26b2",
                "username": "guest-16",
                "name": "Mende"
            },
            "_updatedAt": "2023-03-30T16:58:12.017Z",
            "urls": [],
            "mentions": [],
            "channels": [],
            "md": [
                {
                    "type": "PARAGRAPH",
                    "value": [
                        {
                            "type": "PLAIN_TEXT",
                            "value": "Xup?"
                        }
                    ]
                }
            ],
            "newRoom": false,
            "showConnecting": false
        },
        "metrics": {
            "reaction": {
                "fd": "2023-03-30T16:41:05.370Z",
                "ft": 16.987,
                "tt": 17.112
            },
            "response": {
                "avg": 7.1105,
                "fd": "2023-03-30T16:41:05.370Z",
                "ft": 14.096,
                "total": 2,
                "tt": 14.221
            },
            "v": {
                "lq": "2023-03-30T16:58:11.899Z"
            },
            "servedBy": {
                "lr": "2023-03-30T16:41:05.138Z"
            }
        },
        "servedBy": {
            "_id": "rYhzFRd2QZjNwAAXX",
            "username": "rodriq",
            "ts": "2023-03-30T16:40:48.383Z"
        },
        "waitingResponse": true
    },
    "success": true
}
```
