# Get Team Members

<table><thead><tr><th width="163">HTTP Method</th><th width="272">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/teams.members</code></td><td><a href="../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

This endpoint supports the `offset` and `count` parameters for[#pagination](../../../#pagination "mention") query parameters.

<table><thead><tr><th width="186.33333333333331">Key</th><th width="262">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>teamId</code><mark style="color:red;"><code>*</code></mark> or <code>teamName</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code> or <code>team1</code></td><td>The team ID or the team name. You must enter either one of these parameters.</td></tr><tr><td><code>name</code></td><td><code>Example Name</code></td><td>The user's name (search filter).</td></tr><tr><td><code>username</code></td><td><code>some.username</code></td><td>The username (search filter).</td></tr><tr><td><code>status</code></td><td><code>["online", "away", "busy"]</code></td><td>The user's status (search filter).</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```bash
curl  -H 'X-Auth-Token: _2u_4MzRroRcnqc59GYUY_Kwgr9HgtZ9HCKn-2aIvMJ' \
      -H 'X-User-Id: FL2fZL4ERhwA3gWiS' \
      -H "Content-type: application/json" \
      'http://localhost:3000/api/v1/teams.members?teamName=team1&status[]=online&status=away&status=busy'
```
{% endcode %}

## Example Response

```json
{
  "members": [
    {
      "user": {
        "_id": "FL2fZL4ERhwA3gWiS",
        "username": "some.username",
        "name": "Example Name",
        "status": "online"
      },
      "roles": [
        "owner"
      ],
      "createdBy": {
        "_id": "FL2fZL4ERhwA3gWiS",
        "username": "some.username"
      },
      "createdAt": "2021-04-19T23:09:15.109Z"
    }
  ],
  "total": 3,
  "count": 1,
  "offset": 0,
  "success": true
}
```
