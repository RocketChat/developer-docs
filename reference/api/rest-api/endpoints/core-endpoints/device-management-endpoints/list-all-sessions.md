---
description: List all sessions on the workspace.
---

# List All Sessions

<figure><img src="../../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

Retrieve the sessions of all users on the workspace.  It supports the [Offset, Count, and Sort Query Parameters](../../other-important-endpoints/offset-and-count-and-sort-info.md).

{% hint style="info" %}
* It requires the `view-device-management`[permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
* It requires [two-factor authentication.](../../other-important-endpoints/2fa.md#calling-an-endpoint-with-two-factor)
{% endhint %}

| URL                         | Requires Auth | HTTP Method |
| --------------------------- | ------------- | ----------- |
| `/api/v1/sessions/list.all` | `yes`         | `GET`       |

## Headers

<table><thead><tr><th width="179">Argument</th><th width="239">Example</th><th width="136">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>X-User-Id</code></td><td><code>myuser-name</code></td><td>Required</td><td>The authenticated  user ID.</td></tr><tr><td><code>X-Auth-Token</code></td><td><code>myauth-token</code></td><td>Required</td><td>Auth token.</td></tr><tr><td><code>x-2fa-code</code></td><td><code>148750</code></td><td>Required</td><td>The 2fa code.</td></tr></tbody></table>

## Example Call

```json
curl --location 'http://localhost:3000/api/v1/sessions/list.all' \
--header 'X-Auth-Token: ocFlTSMfowj9tSH1vQV6ANL9SiahkKUK1KhU_PpAUtT' \
--header 'X-User-Id: 2tTEqR7ZNMJ4HGGNa' \
--header 'x-2fa-code: 148750'
```

## Example Result

```json
{
    "sessions": [
        {
            "sessionId": "o94SveQp6fyPsoiNC",
            "userId": "2tTEqR7ZNMJ4HGGNa",
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
            "loginAt": "2023-05-24T00:25:54.234Z",
            "_user": {
                "username": "testroxie",
                "name": "Test"
            },
            "_id": "o94SveQp6fyPsoiNC"
        },
        {
            "sessionId": "BdSrCZXNKCbRi8Eqn",
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
            "loginAt": "2023-05-24T00:25:52.246Z",
            "_user": {
                "username": "funke.olasupo",
                "name": "Funke Olasupo"
            },
            "_id": "BdSrCZXNKCbRi8Eqn"
        },
        {
            "sessionId": "tTouumJMrHMjnedWf",
            "userId": "GonjPyg3gB3Z9ur9s",
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
            "loginAt": "2023-05-23T19:14:29.865Z",
            "_user": {
                "name": "Funke",
                "username": "funke.test"
            },
            "_id": "tTouumJMrHMjnedWf"
        },
        {
            "sessionId": "7ykYEK3KWnk4EeA7s",
            "userId": "2tTEqR7ZNMJ4HGGNa",
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
            "loginAt": "2023-05-23T19:14:28.717Z",
            "_user": {
                "username": "testroxie",
                "name": "Test"
            },
            "_id": "7ykYEK3KWnk4EeA7s"
        },
        {
            "sessionId": "jfD6mnHnrEJdPq9MF",
            "userId": "stjxrXYBWy3EcDugH",
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
            "loginAt": "2023-05-23T15:21:57.188Z",
            "_user": {
                "username": "rocket.agent",
                "name": "Rocket Agent"
            },
            "_id": "jfD6mnHnrEJdPq9MF"
        },
        {
            "sessionId": "2jQnfG74X3EZYL9tj",
            "userId": "rYhzFRd2QZjNwAAXX",
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
            "loginAt": "2023-05-23T15:19:48.723Z",
            "_user": {
                "name": "Rodriq",
                "username": "rodriq"
            },
            "_id": "2jQnfG74X3EZYL9tj"
        },
        {
            "sessionId": "fsfE772s78AmPxGKk",
            "userId": "uZ5JvvioeHK8Coyqe",
            "device": {
                "type": "browser",
                "name": "Firefox",
                "longVersion": "112.0",
                "os": {
                    "name": "Windows",
                    "version": "10"
                },
                "version": "112.0"
            },
            "host": "localhost:3000",
            "ip": "172.18.0.4",
            "loginAt": "2023-05-16T20:50:33.608Z",
            "_user": {
                "username": "user-0"
            },
            "_id": "fsfE772s78AmPxGKk"
        },
        {
            "sessionId": "W4y9xkjyqFvbjENco",
            "userId": "b66oZ8i9pkeSko33v",
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
            "ip": "172.18.0.4",
            "loginAt": "2023-05-16T12:46:09.469Z",
            "_user": {
                "username": "guester",
                "name": "Guester"
            },
            "_id": "W4y9xkjyqFvbjENco"
        },
        {
            "sessionId": "94yTWFkADGBvE9t7P",
            "userId": "aspKK7FHe7iQgzexX",
            "device": {
                "type": "browser",
                "name": "Firefox",
                "longVersion": "112.0",
                "os": {
                    "name": "Windows",
                    "version": "10"
                },
                "version": "112.0"
            },
            "host": "localhost:3000",
            "ip": "172.18.0.4",
            "loginAt": "2023-05-11T18:47:13.865Z",
            "_user": {
                "username": "user-00",
                "name": "User 00"
            },
            "_id": "94yTWFkADGBvE9t7P"
        },
    "total": 13,
    "count": 50,
    "offset": 0,
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **No Permission**: Occurs when the authenticated user doesn't have the  `view-device-management` permission.
* **TOTP Required:** Requires two-factor authentication for the request to be made.
* **Invalid TOTP:** Requires a valid two-factor authentication code.

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
```
{
    "success": false,
    "error": "User does not have the permissions required for this action [error-unauthorized]"
}
```
{% endtab %}

{% tab title="TOTP Required" %}
```
{
    "success": false,
    "error": "TOTP Required [totp-required]",
    "errorType": "totp-required",
    "details": {
        "method": "totp",
        "codeGenerated": false,
        "availableMethods": [
            "totp"
        ]
    }
}
```
{% endtab %}

{% tab title="Invalid TOTP" %}
```
{
    "success": false,
    "error": "TOTP Invalid [totp-invalid]",
    "errorType": "totp-invalid",
    "details": {
        "method": "totp",
        "codeGenerated": false
    }
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 5.0.0   | Added       |
