# Update a Team's Member

Updates a team member's roles. Requires `edit-team-member` permission.

<table><thead><tr><th width="163">HTTP Method</th><th width="289">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/teams.updateMember</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="200.33333333333331">Key</th><th width="258">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>teamId</code><mark style="color:red;"><code>*</code></mark> or <code>teamName</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code> or <code>team1</code></td><td>The team ID or the team name. You must enter either one of these parameters.</td></tr><tr><td><code>members</code><mark style="color:red;"><code>*</code></mark></td><td><code>[{ "userId": "8dugqGhuRvCBLdZft", "roles": ["member"] }]</code></td><td>The users (IDs and roles) to update in the team.</td></tr></tbody></table>

## Example Call

```bash
curl  -H 'X-Auth-Token: _2u_4MzRroRcnqc59GYUY_Kwgr9HgtZ9HCKn-2aIvMJ' \
      -H 'X-User-Id: FL2fZL4ERhwA3gWiS' \
      -H "Content-type: application/json" \
      'http://localhost:3000/api/v1/teams.updateMember' \
      -d '{ 
            "teamName": "team1", 
            "member": { "userId": "LrTDRE27fWPEvaAwC", "roles": ["owner"] } }'
```

## Example Response

```json
{
  "success": true
}
```
