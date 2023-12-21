# Clear Room History

Cleans up a room, removing messages from the provided time range.

<table><thead><tr><th width="163">HTTP Method</th><th width="298">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/rooms.cleanHistory</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameter

<table><thead><tr><th width="208.33333333333331">Key</th><th width="232">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The room ID.</td></tr><tr><td><code>latest</code><mark style="color:red;"><code>*</code></mark></td><td><code>2016-09-30T13:42:25.304Z</code></td><td>The end of time range of messages.</td></tr><tr><td><code>oldest</code><mark style="color:red;"><code>*</code></mark></td><td><code>2016-05-30T13:42:25.304Z</code></td><td>The start of the time range of messages.</td></tr><tr><td><code>inclusive</code></td><td><code>true</code></td><td>Whether messages which land on the latest and oldest dates should be included. By default, the value is <code>false</code>.</td></tr><tr><td><code>excludePinned</code></td><td><code>true</code></td><td>Whether pinned messages should be deleted. By default, the value is <code>false</code>.</td></tr><tr><td><code>filesOnly</code></td><td><code>true</code></td><td>Whether to only delete files and keep messages intact. By default, the value is <code>false</code>.</td></tr><tr><td><code>users</code></td><td><code>["vynmera", "ggazzo"]</code></td><td>Specific set of users whose content to delete. By default, the value is <code>[]</code>, that is, everyone.</td></tr><tr><td><code>limit</code></td><td><code>10</code></td><td>The amount of messages to prune. By default, the value is <code>0</code> (all).</td></tr><tr><td><code>ignoreDiscussion</code></td><td><code>true</code></td><td>Determines if messages from discussions should be pruned. By default, the value is <code>true</code>.</td></tr><tr><td><code>ignoreThreads</code></td><td><code>true</code></td><td>Determines if messages from threads should be pruned. By default, the value is <code>true</code>.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/rooms.cleanHistory \
     -d '{ 
          "roomId": "roomId", 
          "latest": "2016-12-09T13:42:25.304Z", 
          "oldest": "2016-08-30T13:42:25.304Z" }'
```

## Example Response

```json
{
   "success": true
}
```

## Change Log

| Version | Description                                                    |
| ------- | -------------------------------------------------------------- |
| 0.64.0  | Added                                                          |
| 0.67.0  | Added fields `limit`, `excludePinned`, `filesOnly` and `users` |
