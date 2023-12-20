# Get Online Users of Channels

Lists all online users of a channel if the channel's id is provided, otherwise it gets all online users of all channels. It only supports the query parameter for [#query-and-fields](../../../#query-and-fields "mention").

<table><thead><tr><th width="163">HTTP Method</th><th width="320">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/channels.online</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

<table><thead><tr><th width="174.33333333333331">Key</th><th width="303">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>query</code></td><td><code>{"_id":"5HmCfpoB7jp2uibTC"}</code></td><td>See <a href="broken-reference">Query Parameter</a>.</td></tr></tbody></table>

## Example Call

Without query parameter:

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
https://localhost:3000/api/v1/channels.online
```

With query parameter:

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
http://localhost:3000/api/v1/channels.online?query={"_id": "5HmCfpoB7jp2uibTC"}
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
