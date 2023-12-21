# Get Online Group Users

Lists all online users of a group/channel if the group's ID is provided; otherwise, it gets all online users of all groups.

<table><thead><tr><th width="163">HTTP Method</th><th width="324">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/groups.online</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

<table><thead><tr><th width="150">Key</th><th>Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>query</code></td><td><code>{"_id":"5HmCfpoB7jp2uibTC"}</code></td><td>The group ID for which you want to retrieve online users.<br>See <a href="../../../#query-parameters">Query Parameters</a>.</td></tr></tbody></table>

## Example Call

Without query parameter:

```powershell
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
http://localhost:3000/api/v1/groups.online
```

With query parameter:

```powershell
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
http://localhost:3000/api/v1/groups.online?query={"_id": "5HmCfpoB7jp2uibTC"}
```

## Example Response

```json
{
  "online": [
    {
      "_id": "47cRd58HnWwpqxhaZ",
      "username": "test"
    },
    {
      "_id": "BsxzC22xQ43taWdff",
      "username": "uniqueusername"
    }
  ],
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.52.0  | Added       |
