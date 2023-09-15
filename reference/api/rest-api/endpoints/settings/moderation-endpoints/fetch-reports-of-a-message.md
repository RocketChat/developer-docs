# Fetch Reports of a Message

Retrieve all the reports of a single message. A message can have many reports.  It supports the [#pagination](../../../#pagination "mention") parameters.

{% hint style="info" %}
It requires the `view-moderation-console` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
{% endhint %}

| URL                          | Requires Auth | HTTP Method |
| ---------------------------- | ------------- | ----------- |
| `/api/v1/moderation.reports` | `yes`         | `GET`       |

### Headers <a href="#headers" id="headers"></a>

| Argument       | Example        | Required | Description                |
| -------------- | -------------- | -------- | -------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | The authenticated user ID. |
| `X-Auth-Token` | `myauth-token` | Required | Auth token.                |

### Query Parameter <a href="#payload" id="payload"></a>

| Argument | Example             | Required | Description                                 |
| -------- | ------------------- | -------- | ------------------------------------------- |
| `msgId`  | `EbhcT4vjrCDyZuHKq` | Required | The id of the message to fetch reports for. |

### Example Call <a href="#example-call" id="example-call"></a>

```
curl --location 'http://localhost:3000/api/v1/moderation.reports?msgId=EbhcT4vjrCDyZuHKq' \
--header 'x-auth-token: aEO8Hw3zorBFQtAEYsNPnr67Li9-lY5kX1foen8UiiS' \
--header 'x-user-id: rbAXPnMktTFbNpwtJ' \
--data ''
```

### Example Result <a href="#example-result" id="example-result"></a>

### Success

```json
{
    "reports": [
        {
            "_id": "64ef0f992c26843a68c1f785",
            "description": "test report\n",
            "reportedBy": {
                "_id": "rbAXPnMktTFbNpwtJ",
                "username": "funke.olasupo",
                "name": "Funke Olasupo",
                "createdAt": "2023-02-20T13:42:07.119Z"
            },
            "room": {
                "_id": "5fRTXMt7DMJbpPJfhrbAXPnMktTFbNpwtJ",
                "t": "d"
            },
            "ts": "2023-08-30T09:44:57.912Z"
        }
    ],
    "count": 1,
    "offset": 0,
    "total": 1,
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **No Permission:** Occurs when the authenticated user doesn't have the `view-moderation-console` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
* **MessageId Required**: Occurs when `msgId` is missing in the request query parameter.&#x20;

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

{% tab title="Required MsgId" %}
```json
{
    "success": false,
    "error": "must have required property 'msgId' [invalid-params]",
    "errorType": "invalid-params"
}
```
{% endtab %}
{% endtabs %}

### Change Log <a href="#change-log" id="change-log"></a>

| Version | Description |
| ------- | ----------- |
| 6.2.0   | Added       |
