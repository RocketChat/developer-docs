# Remove a Room from Team

<table><thead><tr><th width="163">HTTP Method</th><th width="250">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/teams.removeRoom</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `remove-team-channel`
{% endhint %}

## Body Parameters

<table><thead><tr><th width="195.33333333333331">Key</th><th width="240">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>teamId</code><mark style="color:red;"><code>*</code></mark> or  <code>teamName</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code> or  <code>team1</code></td><td>The team ID or the team name. You must enter either one of these parameters.</td></tr><tr><td><code>roomId</code></td><td><code>8Z7eRsibvD5AANfmK</code></td><td>The room ID to be removed from the team.</td></tr></tbody></table>

## Example Call

```bash
curl  -H 'X-Auth-Token: _2u_4MzRroRcnqc59GYUY_Kwgr9HgtZ9HCKn-2aIvMJ' \
      -H 'X-User-Id: FL2fZL4ERhwA3gWiS' \
      -H "Content-type: application/json" \
      http://localhost:3000/api/v1/teams.removeRoom \
      -d '{ 
            "teamName": "team1", 
            "roomId": "8Z7eRsibvD5AANfmK" }'
```

## Example Response

```json
{
  "room": {
    "_id": "8Z7eRsibvD5AANfmK",
    "name": "roomRemovedFromTheTeam",
    "fname": "roomRemovedFromTheTeam",
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
    "_updatedAt": "2021-04-28T20:57:18.362Z"
  },
  "success": true
}
```
