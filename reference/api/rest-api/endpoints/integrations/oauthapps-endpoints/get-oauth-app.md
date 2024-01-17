# Get OAuth App

Retrieves an OAuth App by ID or client ID.

| URL                      | Requires Auth                            | HTTP Method |
| ------------------------ | ---------------------------------------- | ----------- |
| `/api/v1/oauth-apps.get` | [`yes`](../../authentication-endpoints/) | `GET`       |

{% hint style="info" %}
Permission required: `manage-oauth-apps`
{% endhint %}

## Query Parameters

<table><thead><tr><th width="171">Key</th><th width="237">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>appId</code></td><td><code>jn32kjnnd0943j4njk</code></td><td>The app's ID. This value is required if <code>clientId</code> is not used.</td></tr><tr><td><code>clientId</code></td><td><code>nkn8jk67b8b99b78</code></td><td>The client's ID. This value is required if the <code>appId</code> is not used.</td></tr></tbody></table>

## Example

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/oauth-apps.get?appId=jn32kjnnd0943j4njk
```

## Example Response

```json
{
  "oauthApp": {
    "_id": "zapier",
    "name": "Zapier",
    "active": true,
    "clientId": "zapier",
    "clientSecret": "RTK6TlndaCIolhQhZ7_KHIGOKj41RnlaOq_o-7JKwLr",
    "redirectUri": "https://zapier.com/dashboard/auth/oauth/return/RocketChatDevAPI/",
    "_createdAt": "2019-10-17T22:55:32.787Z",
    "_createdBy": {
      "_id": "system",
      "username": "system"
    },
    "_updatedAt": "2019-10-17T22:55:32.787Z"
  },
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 2.4.0   | Added       |
