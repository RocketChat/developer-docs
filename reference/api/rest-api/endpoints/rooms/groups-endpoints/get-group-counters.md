# Get Group Counters

<table><thead><tr><th width="163">HTTP Method</th><th width="313">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/groups.counters</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

Only one of `roomId` or `roomName` is required.

<table><thead><tr><th width="198.33333333333331">Key</th><th width="237">Example</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>euzoT67Gx6nXcn66M</code></td><td>The group's ID.</td></tr><tr><td><code>roomName</code><mark style="color:red;"><code>*</code></mark></td><td><code>channel.cf.1518990680083</code></td><td>The group's name.</td></tr><tr><td><code>userId</code></td><td><code>RtycPC29hqLJfT9xj</code></td><td>Counters for provided user ID (need to have a <code>view-room-administration</code> right for calling user).</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 8h2mKAwxB3AQrFSjLVKMooJyjdCFaA7W45sWlHP8IzO" \
     -H "X-User-Id: ew28FnZqipDpvKw3R" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/groups.counters?roomId=euzoT67Gx6nXcn66M
```

## Example Response

```json
{
  "joined":true,
  "members":1,
  "unreads":1,
  "unreadsFrom":"2018-02-18T21:51:20.091Z",
  "msgs":1,
  "latest":"2018-02-23T17:20:17.345Z",
  "userMentions":0,
  "success":true
}

//where:

//joined - boolean flag that shows that user is joined the room or not
//members - count of current room members
//unreads - count of unread messages for specified user (calling user or provided userId)
//unreadsFrom - start date-time of unread interval for specified user
//msgs - count of messages in the room
//latest - end date-time of unread interval for specified user (or date-time of last posted message)
//userMentions - count of user mentions in messages
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.65.0  | Added       |
