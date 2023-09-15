# Fetch Info of a Report

Get more details of a single report. A message can be reported multiple times by various users.

{% hint style="info" %}
It requires the `view-moderation-console` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
{% endhint %}

| URL                             | Requires Auth | HTTP Method |
| ------------------------------- | ------------- | ----------- |
| `/api/v1/moderation.reportInfo` | `yes`         | `GET`       |

### Headers <a href="#headers" id="headers"></a>

| Argument       | Example        | Required | Description                |
| -------------- | -------------- | -------- | -------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | The authenticated user ID. |
| `X-Auth-Token` | `myauth-token` | Required | Auth token.                |

### Query Parameter <a href="#payload" id="payload"></a>

| Argument   | Example                    | Required | Description                                |
| ---------- | -------------------------- | -------- | ------------------------------------------ |
| `reportId` | `64ef0f992c26843a68c1f785` | Required | The id of the report to fetch details for. |

### Example Call <a href="#example-call" id="example-call"></a>

```
curl --location 'http://localhost:3000/api/v1/moderation.reportInfo?reportId=64ef0f992c26843a68c1f785' \
--header 'x-auth-token: aEO8Hw3zorBFQtAEYsNPnr67Li9-lY5kX1foen8UiiS' \
--header 'x-user-id: rbAXPnMktTFbNpwtJ' \
--data ''
```

### Example Result <a href="#example-result" id="example-result"></a>

### Success

```json
{
    "report": {
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
        "ts": "2023-08-30T09:44:57.912Z",
        "_updatedAt": "2023-08-30T09:44:57.912Z"
    },
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **No Permission:** Occurs when the authenticated user doesn't have the `view-moderation-console` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
* **ReportId Required**: Occurs when `reportId` is missing in the request query parameter.&#x20;

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

{% tab title="ReportId Required" %}
```json
{
    "success": false,
    "error": "must have required property 'reportId' [invalid-params]",
    "errorType": "invalid-params"
}
```
{% endtab %}
{% endtabs %}

### Change Log <a href="#change-log" id="change-log"></a>

| Version | Description |
| ------- | ----------- |
| 6.2.0   | Added       |
