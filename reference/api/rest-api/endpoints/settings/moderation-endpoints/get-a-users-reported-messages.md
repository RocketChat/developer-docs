# Get a User's Reported Messages

Retrieve all reported messages of a user. It supports the [#pagination](../../../#pagination "mention") parameters.

{% hint style="info" %}
It requires the `view-moderation-console` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
{% endhint %}

| URL                                        | Requires Auth | HTTP Method |
| ------------------------------------------ | ------------- | ----------- |
| `/api/v1/moderation.user.reportedMessages` | `yes`         | `GET`       |

### Headers <a href="#headers" id="headers"></a>

| Argument       | Example        | Required | Description                |
| -------------- | -------------- | -------- | -------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | The authenticated user ID. |
| `X-Auth-Token` | `myauth-token` | Required | Auth token.                |

### Query Parameter <a href="#payload" id="payload"></a>

| Argument | Example             | Required | Description                                                     |
| -------- | ------------------- | -------- | --------------------------------------------------------------- |
| `userId` | `ByehQjC44FwMeiLbX` | Required | The id of the user whose reported messages should be retrieved. |

### Example Call <a href="#example-call" id="example-call"></a>

```
curl --location 'http://localhost:3000/api/v1/moderation.user.reportedMessages?userId=5fRTXMt7DMJbpPJfh' \
--header 'x-auth-token: aEO8Hw3zorBFQtAEYsNPnr67Li9-lY5kX1foen8UiiS' \
--header 'x-user-id: rbAXPnMktTFbNpwtJ' \
--data ''
```

### Example Result <a href="#example-result" id="example-result"></a>

### Success

```json
{
    "user": {
        "_id": "5fRTXMt7DMJbpPJfh",
        "username": "test.funke",
        "name": "TestFunke"
    },
    "messages": [
        {
            "_id": "64ef0f992c26843a68c1f785",
            "message": {
                "_id": "EbhcT4vjrCDyZuHKq",
                "rid": "5fRTXMt7DMJbpPJfhrbAXPnMktTFbNpwtJ",
                "msg": "hola",
                "ts": "2023-08-30T09:44:30.805Z",
                "u": {
                    "_id": "5fRTXMt7DMJbpPJfh",
                    "username": "test.funke",
                    "name": "TestFunke"
                },
                "_updatedAt": "2023-08-30T09:44:30.968Z",
                "urls": [],
                "mentions": [],
                "channels": [],
                "md": [
                    {
                        "type": "PARAGRAPH",
                        "value": [
                            {
                                "type": "PLAIN_TEXT",
                                "value": "hola"
                            }
                        ]
                    }
                ]
            },
            "room": {
                "_id": "5fRTXMt7DMJbpPJfhrbAXPnMktTFbNpwtJ",
                "t": "d"
            },
            "ts": "2023-08-30T09:44:57.912Z"
        },
        {
            "_id": "64ef0cdb2c26843a68c1f780",
            "message": {
                "_id": "xY8cN7yuPQfBgJ9xz",
                "rid": "5fRTXMt7DMJbpPJfhrbAXPnMktTFbNpwtJ",
                "msg": "himm",
                "ts": "2023-07-11T01:37:07.951Z",
                "u": {
                    "_id": "5fRTXMt7DMJbpPJfh",
                    "username": "test.funke",
                    "name": "TestFunke"
                },
                "_updatedAt": "2023-07-11T01:37:08.024Z",
                "urls": [],
                "mentions": [],
                "channels": [],
                "md": [
                    {
                        "type": "PARAGRAPH",
                        "value": [
                            {
                                "type": "PLAIN_TEXT",
                                "value": "himm"
                            }
                        ]
                    }
                ]
            },
            "room": {
                "_id": "5fRTXMt7DMJbpPJfhrbAXPnMktTFbNpwtJ",
                "t": "d"
            },
            "ts": "2023-08-30T09:33:15.621Z"
        }
    ],
    "count": 2,
    "total": 2,
    "offset": 0,
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **No Permission:** Occurs when the authenticated user doesn't have the `view-moderation-console` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).

{% tabs %}
{% tab title="Authorization" %}
```json
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}

{% tab title="No Permission" %}
```json
{
    "success": false,
    "error": "User does not have the permissions required for this action [error-unauthorized]"
}
```
{% endtab %}
{% endtabs %}

### Change Log <a href="#change-log" id="change-log"></a>

| Version | Description |
| ------- | ----------- |
| 6.2.0   | Added       |
