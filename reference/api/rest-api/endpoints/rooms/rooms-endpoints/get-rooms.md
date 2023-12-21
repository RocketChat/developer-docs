# Get Rooms

Get all opened rooms (all joined public & private channels and all DMs) for this user.

<table><thead><tr><th width="163">HTTP Method</th><th width="298">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/rooms.get</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

<table><thead><tr><th width="205.33333333333331">Key</th><th width="235">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>updatedSince</code></td><td><code>2017-11-25T15:08:17.248Z</code></td><td>Rooms that were updated after a specific date. Enter the date as ISO string.</td></tr></tbody></table>

When you provide the `updatedSince` query parameter in the URL, then the `update` and `remove` in the response will contain only those rooms updated and removed since this date and time.

## Example Call

Without query parameters:

```bash
curl -H "X-Auth-Token: ijFlJ1yfidXhwEYY284Anoq_iEsOeMMVCupzNhX22tB" \
     -H "X-User-Id: hw5DThnhQmxDWnavu" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/rooms.get
```

With query parameter:

```bash
curl -H "X-Auth-Token: ijFlJ1yfidXhwEYY284Anoq_iEsOeMMVCupzNhX22tB" \
     -H "X-User-Id: hw5DThnhQmxDWnavu" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/rooms.get?updatedSince=2018-01-26T00:11:22.345Z
```

## Example Result

```javascript
{
   "update": [
      {
         "_id": "GENERAL",
         "name": "general",
         "t": "c",
         "_updatedAt": "2018-01-21T21:03:43.736Z",
         "default": true
      },
      {
         "_id": "3WpJQkDHhrWPBvXuWhw5DThnhQmxDWnavu",
         "t": "d",
         "_updatedAt": "2018-01-21T21:07:16.123Z"
      },
      {
         "_id": "hw5DThnhQmxDWnavurocket.cat",
         "t": "d",
         "_updatedAt": "2018-01-21T21:07:18.510Z"
      },
      {
         "_id": "hw5DThnhQmxDWnavuhw5DThnhQmxDWnavu",
         "t": "d",
         "_updatedAt": "2018-01-21T21:07:20.324Z"
      },
      {
         "_id": "EAemRsye7khfr9Stt",
         "name": "123",
         "fname": "123",
         "t": "p",
         "u":          {
            "_id": "hw5DThnhQmxDWnavu",
            "username": "user2"
         },
         "_updatedAt": "2018-01-24T21:02:04.318Z",
         "customFields": {},
         "ro": false
      }
   ],
   "remove": [],
   "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.62.0  | Added       |
