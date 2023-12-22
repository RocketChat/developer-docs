# Autocomplete Team

List the teams whose names match a given pattern.

<table><thead><tr><th width="163">HTTP Method</th><th width="289">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/teams.autocomplete</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

<table><thead><tr><th width="195.33333333333331">Key</th><th width="227">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>name</code><mark style="color:red;"><code>*</code></mark></td><td><code>team</code></td><td>The pattern (search filter for team names).</td></tr></tbody></table>

## Example Call

```bash
curl  -H 'X-Auth-Token: _2u_4MzRroRcnqc59GYUY_Kwgr9HgtZ9HCKn-2aIvMJ' \
      -H 'X-User-Id: FL2fZL4ERhwA3gWiS' \
      -H "Content-type: application/json" \
      'http://localhost:3000/api/v1/teams.autocomplete?name=team'
```

## Example Response

```json
{
  "teams": [
    {
      "_id": "Dgh2xwJ3NFKWvKSqY",
      "name": "team1",
      "fname": "team1",
      "t": "p",
      "teamId": "607e0d9b49d493189836bfac"
    }
  ],
  "success": true
}
```
