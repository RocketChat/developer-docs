# Get List of Teams

Lists the public and private teams the request sender is part of.&#x20;

<table><thead><tr><th width="163">HTTP Method</th><th width="250">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/teams.list</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

This endpoint supports the[#pagination](../../../#pagination "mention") parameters and the `query` parameter of the[#query-and-fields](../../../#query-and-fields "mention") parameters.

## Example Call

```bash
curl  -H "X-Auth-Token: 8h2mKAwxB3AQrFSjLVKMooJyjdCFaA7W45sWlHP8IzO" \
      -H "X-User-Id: ew28FnZqipDpvKw3R" \
      -H "Content-type: application/json" \
      http://localhost:3000/api/v1/teams.list
```

## Example Response

```json
{
  "teams": [
    {
      "_id": "607e0d9b49d493189836bfac",
      "name": "team1",
      "type": 1,
      "createdAt": "2021-04-19T23:09:15.106Z",
      "createdBy": {
        "_id": "ew28FnZqipDpvKw3R",
        "username": "some.username"
      },
      "_updatedAt": "2021-04-19T23:09:15.106Z",
      "roomId": "Dgh2xwJ3NFKWvKSqY", //team room ID
      "rooms": 2,
      "numberOfUsers": 2
    }
  ],
  "total": 1,
  "count": 1,
  "offset": 0,
  "success": true
}
```

{% hint style="info" %}
`roomId` is the team's main room ID.
{% endhint %}
