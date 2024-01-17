# Delete OAuth App

| URL                         | Requires Auth                            | HTTP Method |
| --------------------------- | ---------------------------------------- | ----------- |
| `/api/v1/oauth-apps.delete` | [`yes`](../../authentication-endpoints/) | `POST`      |

{% hint style="info" %}
Permission required: `manage-oauth-apps`
{% endhint %}

## Body Parameters

<table><thead><tr><th width="199">Key</th><th width="236">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>appId</code><mark style="color:red;"><code>*</code></mark></td><td><code>65a7d77142a7e12453052d59</code></td><td>The OAuth app ID.</td></tr></tbody></table>

## Example Call

```powershell
curl 'http://localhost:3000/api/v1/oauth-apps.create' \
  -H 'Content-Type: application/json' \
  -H 'X-Auth-Token: G1xiui60uWU3A2sRuv0seG3zVKpphJls3NuXVFNDH_o' \
  -H 'X-User-Id: YA5aSHTjZNJEGKHhK' \
  --data-raw '{
        "appId": "65a7d77142a7e12453052d59" }'
```

## Example Response

```json
{
  "success": true
}
```
