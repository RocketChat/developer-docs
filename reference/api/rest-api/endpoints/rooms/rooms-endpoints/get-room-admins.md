# Get Room Admins

Retrieves all rooms.

<table><thead><tr><th width="163">HTTP Method</th><th width="298">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/rooms.adminRooms</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `view-room-administration`
{% endhint %}

## Query Parameters

This endpoint supports the[#pagination](../../../#pagination "mention") parameters. Additional parameters are as follows:

<table><thead><tr><th width="198.33333333333331">Key</th><th width="194">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>types</code></td><td><code>['c']</code></td><td>The room types. The value must be an array.</td></tr><tr><td><code>filter</code></td><td><code>general</code></td><td>The rooms's name.</td></tr></tbody></table>

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
