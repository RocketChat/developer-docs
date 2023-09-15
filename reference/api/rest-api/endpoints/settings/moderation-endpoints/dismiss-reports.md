# Dismiss Reports

You can dismiss all the reports of a particular user by the `userId`. You can also dismiss the report of a message by the `msgId`.

{% hint style="info" %}
It requires the `manage-moderation-actions` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
{% endhint %}

| URL                                 | Requires Auth | HTTP Method |
| ----------------------------------- | ------------- | ----------- |
| `/api/v1/moderation.dismissReports` | `yes`         | `POST`      |

### Headers <a href="#headers" id="headers"></a>

| Argument       | Example        | Required | Description                |
| -------------- | -------------- | -------- | -------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | The authenticated user ID. |
| `X-Auth-Token` | `myauth-token` | Required | Auth token.                |

### Body Parameter <a href="#payload" id="payload"></a>

| Argument | Example             | Required                               | Description                                       |
| -------- | ------------------- | -------------------------------------- | ------------------------------------------------- |
| `userId` | `5fRTXMt7DMJbpPJfh` | Optional, if the `msgId` is provided.  | The `id` of the user whose reports to dismiss.    |
| `msgId`  | `tDNLALSFk2LET2JZH` | Optional, if the `userId` is provided. | The `id` of the message which reports to dismiss. |

{% hint style="info" %}
It requires either the `msgId` or `userId` as a body parameter.
{% endhint %}

### Example Payload <a href="#example-call" id="example-call"></a>

```json
{
    "userId":"5fRTXMt7DMJbpPJfh"
}
```

### Example Call <a href="#example-call" id="example-call"></a>

```
curl --location 'http://localhost:3000/api/v1/moderation.dismissReports' \
--header 'x-auth-token: aEO8Hw3zorBFQtAEYsNPnr67Li9-lY5kX1foen8UiiS' \
--header 'x-user-id: rbAXPnMktTFbNpwtJ' \
--data '{
    "userId":"5fRTXMt7DMJbpPJfh"
}'
```

### Example Result <a href="#example-result" id="example-result"></a>

### Success

```json
{
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
