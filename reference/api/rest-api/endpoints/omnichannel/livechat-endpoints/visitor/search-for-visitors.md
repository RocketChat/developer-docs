# Search for Visitors

Search for visitors using the name, user name, email, or phone.

<table><thead><tr><th width="163">HTTP Method</th><th width="354">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/visitors.search</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

It supports the [#pagination](../../../../#pagination "mention") parameters.

<table><thead><tr><th width="158.33333333333331">Key</th><th width="263">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>term</code></td><td><code>guest-1@company.com</code></td><td>The visitor's name, username, email, or phone.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl http://localhost:3000/api/v1/livechat/visitors.search?term=guest-1@company.com
--header 'X-Auth-Token: Y97tM4GkYjgaH_fIO5dwBitQQvm3yp-AptYzGQZMX6e' \
--header 'X-User-Id: CkCPNcvsvCDfmWLqC'
```
{% endcode %}

## Example Response

```json
{
  "visitors": [
    {
      "_id": "KQv3cHgvW7CDQtGap",
      "username": "guest-1",
      "visitorEmails": [
        {
          "address": "guest-1@company.com"
        }
      ],
      "phone": [
        {
          "phoneNumber": "912235665456"
        }
      ],
      "name": "joey"
    }
  ],
  "count": 1,
  "offset": 0,
  "total": 1,
  "success": true
}
```
