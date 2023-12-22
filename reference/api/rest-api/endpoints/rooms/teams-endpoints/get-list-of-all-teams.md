# Get List of All Teams

Lists all the teams and their information.

<table><thead><tr><th width="163">HTTP Method</th><th width="250">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/teams.listAll</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `view-all-teams`
{% endhint %}

## Query Parameters

This endpoint supports the `offset` and `count` parameters for[#pagination](../../../#pagination "mention").

## Example Call

```bash
curl  -H "X-Auth-Token: 8h2mKAwxB3AQrFSjLVKMooJyjdCFaA7W45sWlHP8IzO" \
      -H "X-User-Id: ew28FnZqipDpvKw3R" \
      -H "Content-type: application/json" \
      http://localhost:3000/api/v1/teams.listAll
```

## Example Response

```json
{
  "teams": [
    {
        "_id": "Isjsldk32sdkfA",
        "name": "team1",
        "type": 0,
        "createdAt": "2016-05-30T13:42:25.304Z"
        "createdBy": {
           "_id": "aobEdbYhXfu5hkeqG",
           "username": "some.username"
        },
        "_updatedAt": "2020-05-21T13:14:07.096Z",
        "roomId": "Dgh2xwJ3NFKWvKSqY",
        "rooms": 2,
        "numberOfUsers": 2
    },
    {
        "_id": "asdf97xcv87",
        "name": "team2",
        "type": 1,
        "createdAt": "2016-05-30T13:42:25.304Z"
        "createdBy": {
           "_id": "aobEdbYhXfu5hkeqG",
           "username": "example"
        },
        "_updatedAt": "2020-05-21T13:14:07.096Z",
        "roomId": "Fda3TghyU03WqsYEv",
        "rooms": 5,
        "numberOfUsers": 4
    }
  ],
  "total": 2,
  "count": 2,
  "offset": 0,
  "success": true
}
```

{% hint style="info" %}
`roomId` is the team's main room ID.
{% endhint %}
