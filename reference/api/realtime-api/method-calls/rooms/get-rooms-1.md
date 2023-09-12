# Get Room By Id

Get room details by room id.

| Name          | Requires Auth | Permission | Setting |
| ------------- | ------------- | ---------- | ------- |
| `getRoomById` | Yes           |            |         |

### Payload Parameters <a href="#payload-parameters" id="payload-parameters"></a>

| Argument | Example              | Required | Description  |
| -------- | -------------------- | -------- | ------------ |
| `rid`    | `siyr2oWQJBjQjhLwru` | Required | The room id. |

## Example call

```javascript
{
    "msg": "method",
    "method": "getRoomById",
    "id": "2",
    "params":[
        "siyr2oWQJBjQjhLwr"
    ]
   
}
```

## Example Response

```javascript
{
    "msg": "result",
    "id": "2",
    "result": {
        "_id": "siyr2oWQJBjQjhLwr",
        "fname": "try",
        "customFields": {},
        "description": "",
        "broadcast": false,
        "encrypted": false,
        "federated": false,
        "name": "try",
        "t": "c",
        "msgs": 10,
        "usersCount": 3,
        "u": {
            "_id": "rbAXPnMktTFbNpwtJ",
            "username": "funke.olasupo"
        },
        "ts": {
            "$date": 1676930439862
        },
        "ro": false,
        "default": false,
        "sysMes": true,
        "_updatedAt": {
            "$date": 1694364133991
        },
        "lastMessage": {
            "rid": "siyr2oWQJBjQjhLwr",
            "ts": {
                "$date": 1689618918246
            },
            "file": {
                "_id": "64b589e6aa5ad4273bfc4db6",
                "name": "eicar.zip",
                "type": "application/x-zip-compressed"
            },
            "files": [
                {
                    "_id": "64b589e6aa5ad4273bfc4db6",
                    "name": "eicar.zip",
                    "type": "application/x-zip-compressed"
                }
            ],
            "attachments": [
                {
                    "ts": "1970-01-01T00:00:00.000Z",
                    "title": "eicar.zip",
                    "title_link": "/file-upload/64b589e6aa5ad4273bfc4db6/eicar.zip",
                    "title_link_download": true,
                    "type": "file",
                    "format": "ZIP",
                    "size": 266
                }
            ],
            "msg": "",
            "groupable": false,
            "u": {
                "_id": "rbAXPnMktTFbNpwtJ",
                "username": "funke.olasupo",
                "name": "Funke Olasupo"
            },
            "_id": "haggP793FFy8jTv2f",
            "_updatedAt": {
                "$date": 1689618918369
            },
            "urls": [],
            "mentions": [],
            "channels": []
        },
        "lm": {
            "$date": 1689618918246
        },
        "muted": [],
        "unmuted": [
            "test.funke"
        ]
    }
}
```
