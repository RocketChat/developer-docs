# Update Room in a Team

<table><thead><tr><th width="163">HTTP Method</th><th width="250">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/teams.updateRoom</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `edit-team-channel`
{% endhint %}

## Body Parameters

<table><thead><tr><th width="190.33333333333331">Key</th><th width="230">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>Dgh2xwJ3NFKWvKSqY</code></td><td>The room id.</td></tr><tr><td><code>isDefault</code><mark style="color:red;"><code>*</code></mark></td><td><code>true</code></td><td>Sets the room as auto-join (<code>true</code>) or not (<code>false</code>).</td></tr></tbody></table>

## Example Call

```bash
curl  -H 'X-Auth-Token: _2u_4MzRroRcnqc59GYUY_Kwgr9HgtZ9HCKn-2aIvMJ' \
      -H 'X-User-Id: FL2fZL4ERhwA3gWiS' \
      -H "Content-type: application/json" \
      http://localhost:3000/api/v1/teams.updateRoom \
      -d '{ 
            "roomId": "8Z7eRsibvD5AANfmK", 
            "isDefault": true }'
```

## Example Response

```json
{
  "room": {
    "_id": "8Z7eRsibvD5AANfmK",
    "name": "channelToUpdate",
    "fname": "channelToUpdate",
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
  },
  "success": true
}
```
