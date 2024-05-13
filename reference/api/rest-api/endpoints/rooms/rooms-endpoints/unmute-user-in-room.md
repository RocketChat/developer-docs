# Unmute User in Room

Unmute a particular user in a room.

<table><thead><tr><th width="163">HTTP Method</th><th width="298">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/rooms.unmuteUser</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="200.33333333333331">Key</th><th width="234">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>JZ8Y2dLfYhsg323Rf</code></td><td>The room ID.</td></tr><tr><td><code>userId</code><mark style="color:red;"><code>*</code></mark></td><td><code>CkCPNfjfhiwWLqC</code></td><td>The user that you want to unmute. Alternatively, you can also use the <code>username</code> parameter.</td></tr></tbody></table>

## Example Call

```bash
curl -L -X POST 'http://localhost:3000/api/v1/rooms.unmuteUser' \
-H 'X-User-Id: d26x6zSkaPSe5gCyy' \
-H 'X-Auth-Token: Zu-Z6eKzIIz7MCCRGeHi29bYkXZCJ4SxFC0JAasqm92' \
-H 'Content-Type: application/json' \
--data-raw '{
    "userId": "CkCPNfjfhiwWLqC",
    "roomId": "iu7jtPAhvEeAS5tNq" 
}'
```

## Example Response

```json
{
    "success": true
}
```

| Version | Description |
| ------- | ----------- |
| 6.8.0   | Added       |
