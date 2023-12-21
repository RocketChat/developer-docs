# Set Group Custom Fields

Sets the custom fields for the group/channel.

<table><thead><tr><th width="180">HTTP Method</th><th width="313">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/groups.setCustomFields</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

Only one of the `roomId` or `roomName` parameters is required.

<table><thead><tr><th width="223.33333333333331">Key</th><th>Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code><mark style="color:red;"><code>*</code></mark></td><td><code>euzoT67Gx6nXcn66M</code></td><td>The group ID.</td></tr><tr><td><code>roomName</code><mark style="color:red;"><code>*</code></mark></td><td><code>channel.cf.1518990680083</code></td><td>The group name.</td></tr><tr><td><code>customFields</code><mark style="color:red;"><code>*</code></mark></td><td><code>{"company": "sell-and-more"}</code></td><td>The custom fields to set for the group.</td></tr></tbody></table>

## Example Call

```bash
curl -H "X-Auth-Token: 8h2mKAwxB3AQrFSjLVKMooJyjdCFaA7W45sWlHP8IzO" \
     -H "X-User-Id: ew28FnZqipDpvKw3R" \
     -H "Content-type: application/json" \
     http://localhost:3000/api/v1/groups.setCustomFields \
     -d '{
          "roomId": "euzoT67Gx6nXcn66M", 
          "customFields":{"company": "sell-and-more"} }'
```

## Example Response

```json
{
  "group":{
    "_id":"euzoT67Gx6nXcn66M",
    "name":"channel.cf.1518990680083",
    "fname":"channel.cf.1518990680083",
    "t":"p",
    "msgs":0,
    "u":{
      "_id":"ew28FnZqipDpvKw3R",
      "username":"rocketchat.internal.admin.test"
    },
    "customFields":{
      "company":"sell-and-more"
    },
    "ts":"2018-02-18T21:51:20.091Z",
    "ro":false,
    "sysMes":true,
    "_updatedAt":"2018-02-23T11:27:01.411Z",
    "username":"rocketchat.internal.admin.test"
  },
  "success":true,
  "developerWarning":"[WARNING]: The \"usernames\" field has been removed for performance reasons. Please use the \"*.members\" endpoint to get a list of members/users in a room."
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.62.0  | Added       |
