# Get Channel Counters

Gets channel information related to a user.

<table><thead><tr><th width="163">HTTP Method</th><th width="339">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/channels.counters</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `view-room-administration`
{% endhint %}

## Query Parameters

<table><thead><tr><th width="204">Key</th><th width="224.33333333333331">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark> or <code>roomName</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code> or <code>GENERAL</code></td><td>The channel room ID or room name. You must enter at least one of the parameters.</td></tr><tr><td><code>userId</code></td><td><code>RtycPC29hqLJfT9xj</code></td><td>The user ID.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 8h2mKAwxB3AQrFSjLVKMooJyjdCFaA7W45sWlHP8IzO" \
     -H "X-User-Id: ew28FnZqipDpvKw3R" \
     -H "Content-type: application/json" \
     https://localhost:3000/api/v1/channels.counters?roomId=ByehQjC44FwMeiLbX
```

## Example Response

```json
{
  "joined":true,
  "members":78,
  "unreads":2,
  "unreadsFrom":"2018-02-23T17:15:51.907Z",
  "msgs":304,
  "latest":"2018-02-23T17:17:03.110Z",
  "userMentions":0,
  "success":true
}

// where:

// joined - boolean flag that shows that user has joined the room or not
// members - count of current room members
// unreads - count of unread messages for specified user (calling user or provided userId)
// unreadsFrom - start date-time of unread interval for specified user
// msgs - count of messages in the room
// latest - end date-time of unread interval for specified user (or date-time of last posted message)
// userMentions - count of user mentions in messages
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.65.0  | Added       |
