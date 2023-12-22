# Create New Team

<table><thead><tr><th width="163">HTTP Method</th><th width="250">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/teams.create</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `create-team`
{% endhint %}

## Body Parameters

<table><thead><tr><th width="175.33333333333331">Key</th><th width="237">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>name</code><mark style="color:red;"><code>*</code></mark></td><td><code>TeamName</code></td><td>The team name.</td></tr><tr><td><code>type</code><mark style="color:red;"><code>*</code></mark></td><td><code>0</code> or <code>1</code></td><td>Privacy of the team (0 - Public, 1 - Private).</td></tr><tr><td><code>members</code></td><td><code>["8dugqGhuRvCBLdZft"]</code></td><td>The user IDs to add to the team when it is created.</td></tr><tr><td><code>room</code></td><td><code>{ readOnly: true }</code></td><td>Additional options used to create the main team channel.</td></tr><tr><td><code>owner</code></td><td><code>CkCPNcvfmWLqC</code></td><td>Set the owner of the team.</td></tr></tbody></table>

## Example Call

```bash
curl  -H "X-Auth-Token: 8h2mKAwxB3AQrFSjLVKMooJyjdCFaA7W45sWlHP8IzO" \
      -H "X-User-Id: ew28FnZqipDpvKw3R" \
      -H "Content-type: application/json" \
      http://localhost:3000/api/v1/teams.create \
      -d '{ 
            "name": "teamName", 
            "type": 0 }'
```

## Example Response

```json
{
  "team": {
    "_id": "608876e583314b02c8e6d857",
    "name": "teamName",
    "type": 0,
    "createdAt": "2021-04-27T20:41:09.738Z",
    "createdBy": {
      "_id": "FL2fZL4ERhwA3gWiS",
      "username": "some.username"
    },
    "_updatedAt": "2021-04-27T20:41:09.738Z",
    "roomId": "yv9KEJdTFjmerZprx"
  },
  "success": true
}
```

{% hint style="info" %}
`roomId` is the team's main room's id.
{% endhint %}
