# Update OAuth App

| URL                         | Requires Auth                            | HTTP Method |
| --------------------------- | ---------------------------------------- | ----------- |
| `/api/v1/oauth-apps.update` | [`yes`](../../authentication-endpoints/) | `POST`      |

{% hint style="info" %}
Permission required: `manage-oauth-apps`
{% endhint %}

## Body Parameters

<table><thead><tr><th width="199">Key</th><th width="206">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>appId</code><mark style="color:red;"><code>*</code></mark></td><td><code>65a7d77142a7e12453052d59</code></td><td>The OAuth app ID.</td></tr><tr><td><code>name</code><mark style="color:red;"><code>*</code></mark></td><td><code>test-oauth-app</code></td><td>The app name that you want to update.</td></tr><tr><td><code>active</code><mark style="color:red;"><code>*</code></mark></td><td><code>true</code></td><td>Whether the app will be active or not. Enter a boolean value, <code>true</code> or <code>false</code>..</td></tr><tr><td><code>redirectUri</code><mark style="color:red;"><code>*</code></mark></td><td><code>https://testuri.com</code></td><td>The URL to redirect the OAuth app.</td></tr></tbody></table>

## Example Call

```powershell
curl 'http://localhost:3000/api/v1/oauth-apps.create' \
  -H 'Content-Type: application/json' \
  -H 'X-Auth-Token: G1xiui60uWU3A2sRuv0seG3zVKpphJls3NuXVFNDH_o' \
  -H 'X-User-Id: YA5aSHTjZNJEGKHhK' \
  --data-raw '{
        "name": "test-oauth-app",
        "redirectUri": "https://testuri.com",
        "active": true,
        "appId": "65a7d77142a7e12453052d59" }'
```

## Example Response

```json
{
  "_id": "65a7d77142a7e12453052d59",
  "name": "test-oauth-app2",
  "redirectUri": "https://testuri2.com",
  "active": false,
  "clientId": "fxHAgLRjP3RswMe67",
  "clientSecret": "QwIAYE1_8M02p-Js8SHZyTPg7HpJm-1ZtbjuSp8bXpP",
  "_createdAt": "2024-01-17T13:34:41.445Z",
  "_updatedAt": "2024-01-17T13:37:16.966Z",
  "_createdBy": {
    "_id": "JFTcMhEAFbNPfnp49",
    "username": "matheus.barbosa"
  },
  "_updatedBy": {
    "_id": "JFTcMhEAFbNPfnp49",
    "username": "matheus.barbosa"
  },
  "success": true
}
```
