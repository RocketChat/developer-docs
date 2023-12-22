# Add Rooms to a Team

<table><thead><tr><th width="163">HTTP Method</th><th width="250">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/teams.addRooms</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `add-team-channel`
{% endhint %}

## Body Parameters

<table><thead><tr><th width="188.33333333333331">Key</th><th width="251">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>teamId</code><mark style="color:red;"><code>*</code></mark> or  <code>teamName</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code> or <code>team1</code></td><td>The team ID or the team name. You must enter either one of the parameters.</td></tr><tr><td><code>rooms</code><mark style="color:red;"><code>*</code></mark></td><td><code>["8dugqGhuRvCBLdZft"]</code></td><td>The IDs of the rooms to be added to the team.</td></tr></tbody></table>

## Example Call

```bash
curl -H 'X-Auth-Token: 8h2mKAwxB3AQrFSjLVKMooJyjdCFaA7W45sWlHP8IzO' \
     -H 'X-User-Id: 8dugqGhuRvCBLdZft' \
     -H 'Content-Type: application/json' \
     http://localhost:3000/api/v1/teams.addRooms \
     -d '{ 
          "teamId": "607e0d9b49d493189836bfac", 
          "rooms": ["8Z7eRsibvD5AANfmK"]}'
```

## Example Response

```json
{
  "rooms": [
    {
      "_id": "8Z7eRsibvD5AANfmK",
      "name": "channelToAddToTeam",
      "fname": "channelToAddToTeam",
      "t": "c",
      "msgs": 0,
      "usersCount": 1,
      "u": {
        "_id": "8dugqGhuRvCBLdZft",
        "username": "some.username"
      },
      "customFields": {},
      "description": "",
      "broadcast": false,
      "encrypted": false,
      "ts": "2021-04-27T19:59:07.258Z",
      "ro": false,
      "_updatedAt": "2021-04-27T19:59:07.313Z",
      "teamId": "607e0d9b49d493189836bfac"
    }
  ],
  "success": true
}
```
