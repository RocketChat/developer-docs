# Remove Member from Team

Requires `edit-team-member` permission.

<table><thead><tr><th width="163">HTTP Method</th><th width="289">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/teams.removeMember</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="200.33333333333331">Key</th><th width="255">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>teamId</code><mark style="color:red;"><code>*</code></mark> or <code>teamName</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code> or <code>team1</code></td><td>The team ID or the team name. You must enter either one of these parameters.</td></tr><tr><td><code>userId</code><mark style="color:red;"><code>*</code></mark></td><td><code>ew28FnZqipDpvKw3R</code></td><td>The user ID to be removed from the team.</td></tr><tr><td><code>rooms</code></td><td><code>["8dugqGhuRvCBLdZft"]</code></td><td>The room IDs from which the user should be removed.</td></tr></tbody></table>

## Example Call

```bash
curl  -H 'X-Auth-Token: _2u_4MzRroRcnqc59GYUY_Kwgr9HgtZ9HCKn-2aIvMJ' \
      -H 'X-User-Id: FL2fZL4ERhwA3gWiS' \
      -H "Content-type: application/json" \
      http://localhost:3000/api/v1/teams.removeMember \
      -d '{ 
            "teamName": "team1", 
            "userId": "kRwRRzfNybEDfQeij" }'
```

## Example Response

```json
{
  "success": true
}
```
