# Get User Canned Responses

<figure><img src="../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

Get a list of all [canned responses](https://docs.rocket.chat/use-rocket.chat/omnichannel/canned-responses) in the workspace that belong to the current user scope. It is helpful for [omnichannel agents](https://docs.rocket.chat/use-rocket.chat/omnichannel/agents) to see all private canned responses that belong to them, canned responses in their departments, and all public canned responses. It supports the [Offset, Count, and Sort Query Parameters](broken-reference).

{% hint style="info" %}
It requires only the `view-canned-responses` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).&#x20;
{% endhint %}

| URL                            | Requires Auth | HTTP Method |
| ------------------------------ | ------------- | ----------- |
| `/api/v1/canned-responses.get` | `yes`         | `GET`       |

## Headers

<table><thead><tr><th width="179">Argument</th><th width="169">Example</th><th width="136">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>X-User-Id</code></td><td><code>myuser-name</code></td><td>Required</td><td>The authenticated  user ID.</td></tr><tr><td><code>X-Auth-Token</code></td><td><code>myauth-token</code></td><td>Required</td><td>Auth token.</td></tr></tbody></table>



## Example Call

```bash
curl --location 'http://localhost:3000/api/v1/canned-responses.get' \
--header 'x-auth-token: heWTP8sY_9EPrmVHclUKT31tttCSpbLzE4JrOYR3qpD' \
--header 'x-user-id: GonjPyg3gB3Z9ur9s'
```

## Example Result

### Success

```javascript
{
    "responses": [
        {
            "_id": "6470086ba8c3a3ba32d0fb1b",
            "shortcut": "department-checking",
            "text": "This is check test for departmental canned response",
            "scope": "global",
            "departmentId": "64181a0728384134ed600dcc",
            "createdBy": {
                "_id": "2tTEqR7ZNMJ4HGGNa",
                "username": "testroxie"
            },
            "_createdAt": "2023-05-26T01:16:27.848Z",
            "_updatedAt": "2023-05-26T01:16:27.848Z"
        },
        {
            "_id": "647009e1a8c3a3ba32d0fb1f",
            "shortcut": "admin-checking",
            "text": "This is check test for departmental canned response",
            "scope": "department",
            "departmentId": "64181a0728384134ed600dcc",
            "createdBy": {
                "_id": "rbAXPnMktTFbNpwtJ",
                "username": "funke.olasupo"
            },
            "_createdAt": "2023-05-26T01:22:41.104Z",
            "_updatedAt": "2023-05-26T01:22:41.104Z"
        },
        {
            "_id": "647009fba8c3a3ba32d0fb21",
            "shortcut": "admin-checking3",
            "text": "This is check test for departmental canned response",
            "scope": "global",
            "departmentId": "64181a0728384134ed600dcc",
            "createdBy": {
                "_id": "rbAXPnMktTFbNpwtJ",
                "username": "funke.olasupo"
            },
            "_createdAt": "2023-05-26T01:23:07.374Z",
            "_updatedAt": "2023-05-26T01:23:07.374Z"
        }
    ],
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **No Permission**: Occurs when the authenticated user doesn't have the  `view-canned-responses`   [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).

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

## Change Log

| Version | Description |
| ------- | ----------- |
| 1.0.0   | Added       |
