# Set Channel Custom Fields

Sets the custom fields for the channel.

<table><thead><tr><th width="163">HTTP Method</th><th width="320">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/channels.setCustomFields</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="206.33333333333331">Key</th><th width="234">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark> or <code>roomName</code><mark style="color:red;"><code>*</code></mark></td><td><code>ew28FnZqipDR</code> or <code>GENERAL</code></td><td>The channel ID or the channel name. You must enter at least one of the parameters.</td></tr><tr><td><code>customFields</code><mark style="color:red;"><code>*</code></mark></td><td><code>{"organization": "tra-la-la"}</code></td><td>The custom fields to set for the channel.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 8h2mKAwxB3AQrFSjLVKMooJyjdCFaA7W45sWlHP8IzO" \
     -H "X-User-Id: ew28FnZqipDpvKw3R" \
     -H "Content-type: application/json" \
     https://localhost:3000/api/v1/channels.setCustomFields \
     -d '{
          "roomId": "GENERAL", 
          "customFields":{"organization": "tra-la-la"} }'
```

## Example Response

```json
{
  "channel":{
    "_id":"GENERAL",
    "ts":"2018-02-18T19:41:02.875Z",
    "t":"c",
    "name":"general",
    "msgs":236,
    "default":true,
    "_updatedAt":"2018-02-23T11:09:05.973Z",
    "lm":"2018-02-18T22:18:20.288Z",
    "customFields":{
      "organization":"tra-la-la"
    }
  },
  "success":true,
  "developerWarning":"[WARNING]: The \"usernames\" field has been removed for performance reasons. Please use the \"*.members\" endpoint to get a list of members/users in a room."
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.62.0  | Added       |
