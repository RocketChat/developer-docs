# Delete a Team

<table><thead><tr><th width="163">HTTP Method</th><th width="289">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/teams.delete</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `delete-team`
{% endhint %}

## Body Parameters

<table><thead><tr><th width="209.33333333333331">Key</th><th width="228">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>teamId</code><mark style="color:red;"><code>*</code></mark> or <code>teamName</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code> <code>team1</code></td><td>The team ID or the team name. You must enter either one of these parameters.</td></tr><tr><td><code>roomsToRemove</code></td><td><code>["8dugqGhuRvCBLdZft"]</code></td><td>The room ID. to delete along with the team.</td></tr></tbody></table>

## Example Call

```bash
curl  -H "X-Auth-Token: 8h2mKAwxB3AQrFSjLVKMooJyjdCFaA7W45sWlHP8IzO" \
      -H "X-User-Id: ew28FnZqipDpvKw3R" \
      -H "Content-type: application/json" \
      http://localhost:3000/api/v1/teams.delete \
      -d '{ 
            "teamId": "Isjsldk32sdkfA" }'
```

## Example Response

```json
{
  "success": true
}
```
