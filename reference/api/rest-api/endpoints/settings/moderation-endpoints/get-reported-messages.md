# Get Reported Messages

Retrieves all the reported messages grouped by users. It supports the [#pagination](../../../#pagination "mention") parameters.

{% hint style="info" %}
It requires the `view-moderation-console` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
{% endhint %}

| URL                                 | Requires Auth | HTTP Method |
| ----------------------------------- | ------------- | ----------- |
| `/api/v1/moderation.reportsByUsers` | `yes`         | `GET`       |

## Headers

<table><thead><tr><th width="179">Argument</th><th width="239">Example</th><th width="136">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>X-User-Id</code></td><td><code>myuser-name</code></td><td>Required</td><td>The authenticated user ID.</td></tr><tr><td><code>X-Auth-Token</code></td><td><code>myauth-token</code></td><td>Required</td><td>Auth token.</td></tr></tbody></table>

## Query Parameter

<table><thead><tr><th width="144">Argument</th><th width="169">Example</th><th>Required</th><th>Description</th></tr></thead><tbody><tr><td><code>oldest</code></td><td><code>2021-09-30T09:33:15.621Z</code></td><td>Optional</td><td>It represents the oldest point in time for which you want to retrieve moderation reports</td></tr><tr><td><code>latest</code></td><td><code>2023-08-30T09:33:15.621Z</code></td><td>Optional</td><td>It represents the oldest point in time for which you want to retrieve moderation reports</td></tr></tbody></table>

## Example Call <a href="#example-call" id="example-call"></a>

```
curl --location 'http://localhost:3000/api/v1/moderation.reportsByUsers' \
--header 'x-auth-token: aEO8Hw3zorBFQtAEYsNPnr67Li9-lY5kX1foen8UiiS' \
--header 'x-user-id: rbAXPnMktTFbNpwtJ' \
--data ''
```

## Example Result <a href="#example-result" id="example-result"></a>

### Success

```json
{
    "reports": [
        {
            "rooms": [
                {
                    "_id": "6423ce62c29657e5b3ba2675rbAXPnMktTFbNpwtJ",
                    "t": "d",
                    "federated": true
                }
            ],
            "count": 1,
            "message": "hi",
            "msgId": "tDNLALSFk2LET2JZH",
            "ts": "2023-08-30T09:38:38.792Z",
            "username": "funke.olasupo",
            "name": "Funke Olasupo",
            "userId": "rbAXPnMktTFbNpwtJ",
            "isUserDeleted": false
        },
        {
            "rooms": [
                {
                    "_id": "5fRTXMt7DMJbpPJfhrbAXPnMktTFbNpwtJ",
                    "t": "d"
                }
            ],
            "count": 2,
            "message": "himm",
            "msgId": "xY8cN7yuPQfBgJ9xz",
            "ts": "2023-08-30T09:33:15.621Z",
            "username": "test.funke",
            "name": "TestFunke",
            "userId": "5fRTXMt7DMJbpPJfh",
            "isUserDeleted": false
        }
    ],
    "count": 2,
    "offset": 0,
    "total": 3,
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **Invalid UserId**: Occurs when the userId is invalid or does not belong to any user in the workspace.
* **No Permission**: Occurs when the authenticated user doesn't have the `view-moderation-console` permission.

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
