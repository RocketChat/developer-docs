---
description: Get sessions of the authenticated user.
---

# Get Current User Sessions

<figure><img src="../../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

Retrieves all sessions of the authenticated user making the request.  It supports the [#pagination](../../../#pagination "mention") parameters.

| URL                     | Requires Auth | HTTP Method |
| ----------------------- | ------------- | ----------- |
| `/api/v1/sessions/list` | `yes`         | `GET`       |

## Headers

<table><thead><tr><th width="179">Argument</th><th width="169">Example</th><th width="136">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>X-User-Id</code></td><td><code>myuser-name</code></td><td>Required</td><td>The authenticated  user ID.</td></tr><tr><td><code>X-Auth-Token</code></td><td><code>myauth-token</code></td><td>Required</td><td>Auth token.</td></tr></tbody></table>

## Query Parameter

<table><thead><tr><th width="144">Argument</th><th width="318">Example</th><th>Required</th><th>Description</th></tr></thead><tbody><tr><td><code>filter</code></td><td>windows</td><td>Optional</td><td>Filter sessions list using regex</td></tr></tbody></table>

## Example Call

```javascript
curl --location 'http://localhost:3000/api/v1/sessions/list' \
--header 'X-Auth-Token: 4uBKb3a7jl28SM1uIAiXnqGvg9CBre9FA8cWxp8AaA6' \
--header 'X-User-Id: rbAXPnMktTFbNpwtJ'
```

## Example Result

### Success

```json
{
    "sessions": [
        {
            "sessionId": "QoYYFw2t9oKks2niG",
            "userId": "rbAXPnMktTFbNpwtJ",
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
            "host": "localhost:3000",
            "ip": "172.20.0.2",
            "loginAt": "2023-05-23T16:33:45.202Z",
            "_id": "QoYYFw2t9oKks2niG"
        },
        {
            "sessionId": "WJ2giBwm4B9mcojFi",
            "userId": "rbAXPnMktTFbNpwtJ",
            "device": {
                "type": "mobile",
                "name": "Chrome",
                "longVersion": "112.0.0.0",
                "os": {
                    "name": "Android",
                    "version": "10"
                },
                "version": "112.0.0"
            },
            "host": "localhost:3000",
            "ip": "172.20.0.2",
            "loginAt": "2023-05-23T12:43:52.023Z",
            "_id": "WJ2giBwm4B9mcojFi"
        }
    ],
    "total": 2,
    "count": 50,
    "offset": 0,
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

## Change Log

| Version | Description |
| ------- | ----------- |
| 5.0.0   | Added       |
