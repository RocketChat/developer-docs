# List User Teams

<table><thead><tr><th width="166">HTTP Method</th><th width="313">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/users.listTeams</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

<table><thead><tr><th width="166">Key</th><th width="269">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>userId</code><mark style="color:red;"><code>*</code></mark></td><td><code>JxemcN9PDCdfzJe</code></td><td>The user ID.</td></tr></tbody></table>

## Example Call

```bash
curl --location --request POST 'http://localhost:3000/api/v1/users.listTeams\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
-d "userId=JxemcN9PDCdfzJe"
```

{% hint style="info" %}
If the caller has permission to view all teams, there's no need to filter the teams.
{% endhint %}

## Example Response

### Success

```json
{
    "teams": [
        {
            "_id": "612b8ae982d286c3",
            "name": "documentation-team",
            "type": 0,
            "createdAt": "2021-08-29T13:26:01.750Z",
            "createdBy": {
                "_id": "JxemcN9PDCdfzJe",
                "username": "renato.b"
            },
            "_updatedAt": "2021-08-29T13:26:01.762Z",
            "roomId": "GwktYAajqw4RiWiBK",
            "isOwner": true
        }
    ],
    "success": true
}
```

### Errors

The following error can occur upon the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.

{% tabs %}
{% tab title=" Authorization" %}
```json
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}
{% endtabs %}
