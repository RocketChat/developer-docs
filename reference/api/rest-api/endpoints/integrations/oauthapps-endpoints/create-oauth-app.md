# Create OAuth App

| URL                         | Requires Auth                            | HTTP Method |
| --------------------------- | ---------------------------------------- | ----------- |
| `/api/v1/oauth-apps.create` | [`yes`](../../authentication-endpoints/) | `POST`      |

{% hint style="info" %}
Permission required: `manage-oauth-apps`
{% endhint %}

## Body Parameters

<table><thead><tr><th width="199">Key</th><th width="206">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>name</code><mark style="color:red;"><code>*</code></mark></td><td><code>test-oauth-app</code></td><td>The app name that you want to create.</td></tr><tr><td><code>active</code><mark style="color:red;"><code>*</code></mark></td><td><code>true</code></td><td>Whether the app will be active or not. Enter a boolean value, <code>true</code> or <code>false</code>..</td></tr><tr><td><code>redirectUri</code><mark style="color:red;"><code>*</code></mark></td><td><code>https://testuri.com</code></td><td>The URL to redirect the OAuth app.</td></tr></tbody></table>

## Example Call

```powershell
curl 'http://localhost:3000/api/v1/oauth-apps.create' \
  -H 'Content-Type: application/json' \
  -H 'X-Auth-Token: G1xiui60uWU3A2sRuv0seG3zVKpphJls3NuXVFNDH_o' \
  -H 'X-User-Id: YA5aSHTjZNJEGKHhK' \
  --data-raw '{
        "name": "test-oauth-app",
        "redirectUri": "https://testuri.com",
        "active": true }'
```

## Example Response

```json
{
  "application": {
    "name": "test-oauth-app",
    "redirectUri": "https://testuri.com",
    "active": true,
    "clientId": "bN9D5TjY8Cv8GqWfE",
    "clientSecret": "l3HAl0lSr2VaTYZVED6EabyhNzovS8Je2JYmbjNT-V1",
    "_createdAt": "2024-01-17T13:30:41.521Z",
    "_updatedAt": "2024-01-17T13:30:41.521Z",
    "_createdBy": {
      "_id": "JFTcMhEAFbNPfnp49",
      "username": "math.bar"
    },
    "_id": "65a7d68142a7e12453052d56"
  },
  "success": true
}
```
