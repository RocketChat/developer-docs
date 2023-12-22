# Update a Team

Updates an existing team (name and type). Requires `edit-team` permission.

<table><thead><tr><th width="163">HTTP Method</th><th width="289">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/teams.update</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body Parameters

<table><thead><tr><th width="189.33333333333331">Key</th><th>Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>teamId</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The team ID.</td></tr><tr><td><code>data</code><mark style="color:red;"><code>*</code></mark></td><td><code>{ "name": "newTeamName", "type": 1 }</code></td><td>The new team name and type (0 - public, 1 - private).</td></tr></tbody></table>

## Example Call

```bash
curl -H 'X-Auth-Token: _2u_4MzRroRcnqc59GYUY_Kwgr9HgtZ9HCKn-2aIvMJ' \
     -H 'X-User-Id: FL2fZL4ERhwA3gWiS' \
     -H 'Content-Type: application/json' \
     http://localhost:3000/api/v1/teams.update \
     -d '{ 
          "teamId": "ByehQjC44FwMeiLbX", 
          "data": { "name": "newTeamName", "type": 1 }}'
```

## Example Response

```json
{
  "success": true
}
```
