---
description: Get session info for the authenticated user
---

# Get Current User Session Information

<figure><img src="../../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

Retrieve session information for sessions owned by the authenticated user. This endpoint provides detailed information about the user's sessions on the workspace. It does not grant access to the session information of other users on the workspace.

| URL                     | Requires Auth | HTTP Method |
| ----------------------- | ------------- | ----------- |
| `/api/v1/sessions/info` | `yes`         | `GET`       |

## Headers

<table><thead><tr><th width="179">Argument</th><th width="169">Example</th><th width="136">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>X-User-Id</code></td><td><code>myuser-name</code></td><td>Required</td><td>The authenticated  user ID.</td></tr><tr><td><code>X-Auth-Token</code></td><td><code>myauth-token</code></td><td>Required</td><td>Auth token.</td></tr></tbody></table>

## Query Parameters

| Argument    | Example           | Required | Description     |
| ----------- | ----------------- | -------- | --------------- |
| `sessionId` | QoYYFw2t9oKks2niG | Required | The session id. |

## Example Call

```javascript
curl --location 'http://localhost:3000/api/v1/sessions/info?sessionId=QoYYFw2t9oKks2niG' \
--header 'X-Auth-Token: 4uBKb3a7jl28SM1uIAiXnqGvg9CBre9FA8cWxp8AaA6' \
--header 'X-User-Id: rbAXPnMktTFbNpwtJ'
```

## Example Result

### Success

```json
{
    "_id": "646ceae9a8c3a3ba32d0e897",
    "type": "session",
    "sessionId": "QoYYFw2t9oKks2niG",
    "instanceId": "f0313fa9-ebe6-4a84-8580-3104f6a09988",
    "loginToken": "orklPYtfnjnG6mG7OMuLbOBDzs8I9myfcLl2yzv7WoU=",
    "ip": "172.20.0.2",
    "host": "localhost:3000",
    "device": {
        "type": "browser",
        "name": "Chrome",
        "longVersion": "113.0.0.0",
        "os": {
            "name": "Windows",
            "version": "10"
        },
        "version": "113.0.0"
    },
    "userId": "rbAXPnMktTFbNpwtJ",
    "roles": [
        "user",
        "admin",
        "livechat-agent",
        "livechat-manager"
    ],
    "mostImportantRole": "admin",
    "loginAt": "2023-05-23T16:33:45.202Z",
    "day": 23,
    "month": 5,
    "year": 2023,
    "searchTerm": "ChromebrowserWindowsQoYYFw2t9oKks2niGrbAXPnMktTFbNpwtJ",
    "createdAt": "2023-05-23T16:33:45.203Z",
    "_updatedAt": "2023-05-23T17:56:31.599Z",
    "closedAt": "2023-05-23T17:56:31.599Z",
    "lastActivityAt": "2023-05-23T17:56:31.599Z",
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **Session not found:**  Occurs when the `sessionId` doesn't belong to the current user making the request or does not exist.

{% tabs %}
{% tab title="Authorization" %}
```json
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}

{% tab title="Session not found" %}
```json
{
    "success": false,
    "error": "Session not found"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 5.0.0   | Added       |
