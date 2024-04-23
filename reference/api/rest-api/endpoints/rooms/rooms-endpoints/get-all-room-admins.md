# Get All Room Admins

Retrieves all rooms and admin information.

<table><thead><tr><th width="163">HTTP Method</th><th width="298">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/rooms.adminRooms</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `view-room-administration`
{% endhint %}

## Query Parameters

This endpoint supports the [#pagination](../../../#pagination "mention") parameters. Additional parameters are as follows:

<table><thead><tr><th width="179.33333333333331">Key</th><th width="194">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>types</code></td><td><code>c</code></td><td><p>The room types. The possible room types are:</p><ul><li><code>d</code>: Direct messages</li><li><code>c</code>: Public channel</li><li><code>p</code>: Private channel</li><li><code>discussions</code>: Team or channel discussions</li><li><code>teams</code>: Workspace teams</li><li><code>l</code>: Livechat</li><li><code>v</code>: Omnichannel VoIP rooms</li></ul></td></tr><tr><td><code>filter</code></td><td><code>general</code></td><td>The rooms's name.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: ijFlJ1yfidXhwEYY284Anoq_iEsOeMMVCupzNhX22tB" \
     -H "X-User-Id: hw5DThnhQmxDWnavu" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/rooms.adminRooms?types[]=c&types[]=p&filter=GENERAL
```

## Example Response

```json
{
    "rooms": [
        {
            "_id": "654c9d1ca2f73c7460e1918b",
            "fname": "animalGeography",
            "topic": "",
            "broadcast": false,
            "name": "animalGeography",
            "t": "p",
            "msgs": 4,
            "usersCount": 1,
            "u": {
                "_id": "CkCPNcvsvCDfmWLqC",
                "username": "kim.jane",
                "name": "kim.jane"
            },
            "ro": false,
            "default": false
        }
    ],
    "count": 1,
    "offset": 0,
    "total": 1,
    "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 2.4.0   | Added       |
