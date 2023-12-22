# List Rooms of a Team

List all rooms of the team.

<table><thead><tr><th width="163">HTTP Method</th><th width="272">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/teams.listRooms</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

This endpoint supports the `offset` and `count` parameter for[#pagination](../../../#pagination "mention") parameters.

<table><thead><tr><th width="196.33333333333331">Key</th><th width="245">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>teamId</code><mark style="color:red;"><code>*</code></mark> or <code>teamName</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code> or <code>team1</code></td><td>The team ID or the team name. You must enter either one of these parameters.</td></tr><tr><td><code>filter</code></td><td><code>Example Room Name</code></td><td>The room's name (search filter).</td></tr><tr><td><code>type</code></td><td><code>autoJoin</code></td><td>The room's type (search filter).</td></tr></tbody></table>

## Example Call

```bash
curl  -H 'X-Auth-Token: _2u_4MzRroRcnqc59GYUY_Kwgr9HgtZ9HCKn-2aIvMJ' \
      -H 'X-User-Id: FL2fZL4ERhwA3gWiS' \
      -H "Content-type: application/json" \
      'http://localhost:3000/api/v1/teams.listRooms?teamName=team1&type=autoJoin'
```

## Example Response

```json
{
  "rooms": [
    {
      "_id": "8Z7eRsibvD5AANfmK",
      "name": "channelAutoJoin",
      "fname": "channelAutoJoin",
      "t": "c",
      "msgs": 7,
      "usersCount": 1,
      "u": {
        "_id": "FL2fZL4ERhwA3gWiS",
        "username": "some.username"
      },
      "customFields": {},
      "description": "",
      "broadcast": false,
      "encrypted": false,
      "ts": "2021-04-27T19:59:07.258Z",
      "ro": false,
      "_updatedAt": "2021-04-28T20:57:18.362Z",
      "teamId": "607e0d9b49d493189836bfac",
      "teamDefault": true
    }
  ],
  "total": 1,
  "count": 1,
  "offset": 0,
  "success": true
}
```
