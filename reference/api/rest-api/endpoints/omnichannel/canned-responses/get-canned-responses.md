# Get User Canned Responses

<figure><img src="../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Get a list of all [canned responses](https://docs.rocket.chat/use-rocket.chat/omnichannel/canned-responses) in the workspace that belong to the current user scope.

<table><thead><tr><th width="163">HTTP Method</th><th width="332">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/canned-responses.get</code></td><td><a href="../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `view-canned-responses`
{% endhint %}

## Example Call

```powershell
curl --location 'http://localhost:3000/api/v1/canned-responses.get' \
--header 'x-auth-token: heWTP8sY_9EPrmVHclUKT31tttCSpbLzE4JrOYR3qpD' \
--header 'x-user-id: GonjPyg3gB3Z9ur9s'
```

## Example Response

### Success

```json
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
                "username": "kim.jane"
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
                "username": "doe.john"
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
