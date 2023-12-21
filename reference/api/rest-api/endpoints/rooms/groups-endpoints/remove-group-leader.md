# Remove Group Leader

Removes the role of Leader for a user in the current group/channel.

<table><thead><tr><th width="180">HTTP Method</th><th width="313">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/groups.removeLeader</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="199.33333333333331">Key</th><th width="246">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The group ID.</td></tr><tr><td><code>userId</code><mark style="color:red;"><code>*</code></mark></td><td><code>oCHkav5Zf6vmpu2W2</code></td><td>The user ID.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/groups.removeLeader \
     -d '{
          "roomId": "ByehQjC44FwMeiLbX", 
          "userId": "oCHkav5Zf6vmpu2W2"}'
```

## Example Response

### Success

```json
{
    "success": true
}
```

### Error

If the user is not a leader, will return a `400 bad request` status.

```json
{
    "success": false,
    "error": "User is not a leader [error-user-not-leader]",
    "errorType": "error-user-not-leader"
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.58.0  | Added.      |
