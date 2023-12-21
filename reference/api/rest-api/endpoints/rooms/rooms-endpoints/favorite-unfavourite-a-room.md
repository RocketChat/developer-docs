# Favorite/Unfavourite a Room

<table><thead><tr><th width="163">HTTP Method</th><th width="298">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/rooms.favorite</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="199.33333333333331">Key</th><th width="231">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark> or <code>roomName</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The room ID.</td></tr><tr><td><code>favorite</code><mark style="color:red;"><code>*</code></mark> </td><td><code>true</code></td><td>A boolean to mark the room as favourite or not.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-Type: application/json" \
     http://localhost:3000/api/v1/rooms.favorite  \
     -d '{ 
          "roomId": "GENERAL", 
          "favorite": true }'
```

## Example Response

```json
{
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.64.0  | Added       |
