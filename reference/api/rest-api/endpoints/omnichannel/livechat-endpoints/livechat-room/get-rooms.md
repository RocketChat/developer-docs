# Get Rooms

Gets a list of all the current Live chat rooms

<table><thead><tr><th width="309.3333333333333">URL</th><th>Requires Auth</th><th>HTTP Method</th></tr></thead><tbody><tr><td><code>/api/v1/livechat/rooms</code></td><td><code>yes</code></td><td><code>GET</code></td></tr></tbody></table>

## Example Call

{% tabs %}
{% tab title="Curl" %}
```
curl --location --request GET 'http://localhost:3000/api/v1/livechat/rooms' \
--header 'X-Auth-Token: OsLBoPh6cUgNuh6mWT8z4VIY_nGl8R30XVE4QNDLT6S' \
--header 'X-User-Id: f5vPj6jfkRXipkwoC'
```
{% endtab %}

{% tab title="Node js" %}
```javascript
var request = require('request');
var options = {
  'method': 'GET',
  'url': 'http://localhost:3000/api/v1/livechat/rooms',
  'headers': {
    'X-Auth-Token': 'OsLBoPh6cUgNuh6mWT8z4VIY_nGl8R30XVE4QNDLT6S',
    'X-User-Id': 'f5vPj6jfkRXipkwoC'
  }
};
request(options, function (error, response) {
  if (error) throw new Error(error);
  console.log(response.body);
});

```
{% endtab %}

{% tab title="Python" %}
```python
import requests

url = "http://localhost:3000/api/v1/livechat/rooms"

payload={}
headers = {
  'X-Auth-Token': 'OsLBoPh6cUgNuh6mWT8z4VIY_nGl8R30XVE4QNDLT6S',
  'X-User-Id': 'f5vPj6jfkRXipkwoC'
}

response = requests.request("GET", url, headers=headers, data=payload)

print(response.text)
```
{% endtab %}
{% endtabs %}

## Example Result

### Success

```json
{
    "rooms": [
        {
            "_id": "gMMeBpWyLeowCrzBv",
            "msgs": 2,
            "usersCount": 1,
            "lm": "2022-11-21T09:30:57.164Z",
            "fname": "Elsie Teng",
            "t": "l",
            "ts": "2022-11-21T09:30:56.209Z",
            "v": {
                "_id": "637b4534d3cc906f14f967dd",
                "username": "guest-3",
                "token": "d4a8338e5a7d98b6750b4f839431b34a3f4813b2c43f7d89597948f21f607bb4",
                "status": "offline",
                "lastMessageTs": "2022-11-21T09:30:57.164Z"
            },
            "cl": false,
            "open": true,
            "source": {
                "type": "widget"
            },
            "queuedAt": "2022-11-21T09:30:56.209Z",
            "_updatedAt": "2022-11-21T10:08:38.351Z",
            "lastMessage": {
                "_id": "JdMjSyMyfNHpmurik",
                "rid": "gMMeBpWyLeowCrzBv",
                "msg": "Hello there",
                "token": "d4a8338e5a7d98b6750b4f839431b34a3f4813b2c43f7d89597948f21f607bb4",
                "alias": "Elsie Teng",
                "ts": "2022-11-21T09:30:57.164Z",
                "u": {
                    "_id": "637b4534d3cc906f14f967dd",
                    "username": "guest-3",
                    "name": "Elsie Teng"
                },
                "_updatedAt": "2022-11-21T09:30:57.256Z",
                "urls": [],
                "mentions": [],
                "channels": [],
                "md": [
                    {
                        "type": "PARAGRAPH",
                        "value": [
                            {
                                "type": "PLAIN_TEXT",
                                "value": "Hello there"
                            }
                        ]
                    }
                ],
                "newRoom": false,
                "showConnecting": true
            },
            "metrics": {
                "reaction": {
                    "fd": "2022-11-21T09:30:56.312Z",
                    "ft": 0.103,
                    "tt": 0.103
                },
                "response": {
                    "avg": 0.103,
                    "fd": "2022-11-21T09:30:56.312Z",
                    "ft": 0.103,
                    "total": 1,
                    "tt": 0.103
                }
            },
            "waitingResponse": true
        },
        {
            "_id": "oY5N73aGJK7rn9THa",
            "fname": "Murtaza P",
            "t": "l",
            "v": {
                "_id": "6374a855d3cc906f14f967c1",
                "username": "917738772967",
                "token": "31n6zyumwtmhhhhp69q4v",
                "status": "online"
            },
            "default": false,
            "ro": false,
            "sysMes": true,
            "open": true,
            "msgs": 4,
            "ts": "2022-11-16T09:11:27.445Z",
            "_updatedAt": "2022-11-16T09:11:51.226Z",
            "lm": "2022-11-16T09:11:51.103Z",
            "customFields": {
                "whatsAppCloudMessage": {
                    "visitorWaId": "917738772967",
                    "contactWaId": "100140772718747"
                },
                "whatsAppCloudSessionExpiration": "2022-11-17T09:11:27.718Z"
            },
            "source": {
                "type": "app",
                "id": "5e3dadaa-e774-40d8-b3a4-b93b91747168",
                "alias": "WhatsApp Cloud",
                "label": "+1 555-036-6171",
                "sidebarIcon": "whatsapp",
                "defaultIcon": "whatsapp"
            },
            "usersCount": 2,
            "cl": false,
            "queuedAt": "2022-11-16T09:11:27.445Z",
            "lastMessage": {
                "_id": "ZMiAMYMtFHnCFAcxL",
                "rid": "oY5N73aGJK7rn9THa",
                "msg": "Hello WhatsApp!",
                "ts": "2022-11-16T09:11:51.103Z",
                "u": {
                    "_id": "jXb2wWc9596RhN4nd",
                    "username": "murtaza1",
                    "name": "murtaza"
                },
                "_updatedAt": "2022-11-16T09:11:51.191Z",
                "urls": [],
                "mentions": [],
                "channels": [],
                "md": [
                    {
                        "type": "PARAGRAPH",
                        "value": [
                            {
                                "type": "PLAIN_TEXT",
                                "value": "Hello WhatsApp!"
                            }
                        ]
                    }
                ]
            },
            "metrics": {
                "reaction": {
                    "fd": "2022-11-16T09:11:51.204Z",
                    "ft": 16.817,
                    "tt": 16.889
                },
                "response": {
                    "avg": 11.9155,
                    "fd": "2022-11-16T09:11:51.204Z",
                    "ft": 23.759,
                    "total": 2,
                    "tt": 23.831
                }
            },
            "servedBy": {
                "_id": "jXb2wWc9596RhN4nd",
                "username": "murtaza1",
                "ts": "2022-11-16T09:11:34.387Z"
            },
            "responseBy": {
                "_id": "jXb2wWc9596RhN4nd",
                "username": "murtaza1",
                "lastMessageTs": "2022-11-16T09:11:51.203Z"
            }
        },
        {
            "_id": "rFbuWtpdyS5gQguLu",
            "fname": "Murtaza P",
            "t": "l",
            "v": {
                "_id": "6374a855d3cc906f14f967c1",
                "username": "917738772967",
                "token": "31n6zyumwtmhhhhp69q4v",
                "status": "offline"
            },
            "servedBy": {
                "_id": "gGbSgoqvAodNMn6W9",
                "username": "test.user"
            },
            "default": false,
            "ro": false,
            "sysMes": true,
            "msgs": 11,
            "ts": "2022-11-16T09:07:33.772Z",
            "_updatedAt": "2022-11-16T09:09:32.617Z",
            "lm": "2022-11-16T09:09:32.529Z",
            "customFields": {
                "whatsAppCloudMessage": {
                    "visitorWaId": "917738772967",
                    "contactWaId": "100140772718747"
                },
                "whatsAppCloudSessionExpiration": "2022-11-17T09:08:43.691Z"
            },
            "source": {
                "type": "app",
                "id": "5e3dadaa-e774-40d8-b3a4-b93b91747168",
                "alias": "WhatsApp Cloud",
                "label": "+1 555-036-6171",
                "sidebarIcon": "whatsapp",
                "defaultIcon": "whatsapp"
            },
            "usersCount": 1,
            "cl": false,
            "queuedAt": "2022-11-16T09:07:33.772Z",
            "lastMessage": {
                "t": "livechat-close",
                "msg": "this is pretty cool!!!",
                "groupable": false,
                "transcriptRequested": false,
                "ts": "2022-11-16T09:09:32.529Z",
                "u": {
                    "_id": "jXb2wWc9596RhN4nd",
                    "username": "murtaza1",
                    "name": "murtaza"
                },
                "rid": "rFbuWtpdyS5gQguLu",
                "_id": "62k5dj2rYcCt2vq5o",
                "_updatedAt": "2022-11-16T09:09:32.593Z",
                "urls": [],
                "mentions": [],
                "channels": [],
                "md": [
                    {
                        "type": "PARAGRAPH",
                        "value": [
                            {
                                "type": "PLAIN_TEXT",
                                "value": "this is pretty cool!!!"
                            }
                        ]
                    }
                ]
            },
            "metrics": {
                "reaction": {
                    "fd": "2022-11-16T09:09:32.604Z",
                    "ft": 118.832,
                    "tt": 196.134
                },
                "response": {
                    "avg": 49.0335,
                    "fd": "2022-11-16T09:09:32.604Z",
                    "ft": 118.832,
                    "total": 4,
                    "tt": 196.134
                },
                "chatDuration": 118.686
            },
            "closedAt": "2022-11-16T09:09:32.458Z",
            "closedBy": {
                "_id": "jXb2wWc9596RhN4nd",
                "username": "murtaza1"
            },
            "closer": "user",
            "tags": [],
            "responseBy": {
                "_id": "jXb2wWc9596RhN4nd",
                "username": "murtaza1",
                "lastMessageTs": "2022-11-16T09:09:32.603Z"
            }
        },
        {
            "_id": "YbYjBtCAn2peDmWeA",
            "fname": "Rodriq",
            "t": "l",
            "v": {
                "_id": "637353b7d3cc906f14f967ac",
                "username": "23778769140",
                "token": "ylprp58ilg3uj4f947k6w",
                "status": "online"
            },
            "servedBy": {
                "_id": "gGbSgoqvAodNMn6W9",
                "username": "test.user"
            },
            "default": false,
            "ro": false,
            "sysMes": true,
            "open": true,
            "msgs": 7,
            "ts": "2022-11-15T08:54:15.768Z",
            "_updatedAt": "2022-11-15T08:57:48.939Z",
            "lm": "2022-11-15T08:57:48.831Z",
            "customFields": {
                "whatsAppCloudMessage": {
                    "visitorWaId": "23778769140",
                    "contactWaId": "104258779177044"
                },
                "whatsAppCloudSessionExpiration": "2022-11-16T08:57:07.419Z"
            },
            "source": {
                "type": "app",
                "id": "5e3dadaa-e774-40d8-b3a4-b93b91747168",
                "alias": "WhatsApp Cloud",
                "label": "+1 555-011-6179",
                "sidebarIcon": "whatsapp",
                "defaultIcon": "whatsapp"
            },
            "usersCount": 2,
            "cl": false,
            "queuedAt": "2022-11-15T08:54:15.768Z",
            "lastMessage": {
                "_id": "RBzMhkfLaR84j2txs",
                "rid": "YbYjBtCAn2peDmWeA",
                "msg": "kl",
                "ts": "2022-11-15T08:57:48.831Z",
                "u": {
                    "_id": "gGbSgoqvAodNMn6W9",
                    "username": "test.user",
                    "name": "testing"
                },
                "_updatedAt": "2022-11-15T08:57:48.905Z",
                "urls": [],
                "mentions": [],
                "channels": [],
                "md": [
                    {
                        "type": "PARAGRAPH",
                        "value": [
                            {
                                "type": "PLAIN_TEXT",
                                "value": "kl"
                            }
                        ]
                    }
                ]
            },
            "metrics": {
                "reaction": {
                    "fd": "2022-11-15T08:57:48.917Z",
                    "ft": 213.149,
                    "tt": 296.716
                },
                "response": {
                    "avg": 98.90533333333333,
                    "fd": "2022-11-15T08:57:48.917Z",
                    "ft": 213.149,
                    "total": 3,
                    "tt": 296.716
                }
            },
            "responseBy": {
                "_id": "gGbSgoqvAodNMn6W9",
                "username": "test.user",
                "lastMessageTs": "2022-11-15T08:57:48.915Z"
            }
        }
    ],
    "count": 4,
    "offset": 0,
    "total": 4,
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.

{% tabs %}
{% tab title="Authorization" %}
```json
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}
{% endtabs %}
