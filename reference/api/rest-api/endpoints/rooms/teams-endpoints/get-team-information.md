# Get Team Information

Gets a team's information. If the team is not public, the request sender must be a member of the team.

<table><thead><tr><th width="163">HTTP Method</th><th width="289">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/teams.info</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

<table><thead><tr><th width="198.33333333333331">Key</th><th width="251">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>teamId</code><mark style="color:red;"><code>*</code></mark> or <code>teamName</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code> or <code>team1</code></td><td>The team ID or the team name. You must enter either one of these parameters.</td></tr></tbody></table>

## Example Call

```bash
curl  -H "X-Auth-Token: 8h2mKAwxB3AQrFSjLVKMooJyjdCFaA7W45sWlHP8IzO" \
      -H "X-User-Id: ew28FnZqipDpvKw3R" \
      -H "Content-type: application/json" \
      http://localhost:3000/api/v1/teams.info?teamName=Team1
```

## Example Response

```json
{
  "teamInfo": {
    "_id": "607e0d9b49d493189836bfac",
    "name": "Team1",
    "type": 1,
    "createdAt": "2021-04-19T23:09:15.106Z",
    "createdBy": {
      "_id": "FL2fZL4ERhwA3gWiS",
      "username": "some.username"
    },
    "_updatedAt": "2021-04-19T23:09:15.106Z",
    "roomId": "Dgh2xwJ3NFKWvKSqY"
  },
  "success": true
}
```

{% hint style="info" %}
`roomId` is the team's main room ID.
{% endhint %}
