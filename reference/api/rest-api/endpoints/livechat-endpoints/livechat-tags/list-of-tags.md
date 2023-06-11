---
description: Gives a list of tags
---

# List of Tags

![](../../../../../../../.gitbook/assets/enterprise.jpg)

{% hint style="info" %}
![](../../../../../../../.gitbook/assets/Deprecated.png) This endpoint has been renamed to [get-tags.md](get-tags.md "mention") as from Rocket.Chat `5.0`
{% endhint %}

| URL                         | Requires Auth | HTTP Method |
| --------------------------- | ------------- | ----------- |
| `api/v1/livechat/tags.list` | `YES`         | `GET`       |

## Headers

<table><thead><tr><th width="177">Argument</th><th>Example</th><th>Required</th><th>Description</th></tr></thead><tbody><tr><td><code>X-User-Id</code></td><td><code>myuser-name</code></td><td>Required</td><td>Your username hash (returned after you log in through the API)</td></tr><tr><td><code>X-Auth-Token</code></td><td><code>myauth-token</code></td><td>Required</td><td>Your token (returned after you log in through the API)</td></tr></tbody></table>

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/livechat/tags.list\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript
{
    "tags": [
        {
            "_id": "pXkCRLGxD34y2FEZq",
            "name": "Valuable  lead",
            "description": "high chances of conversion",
            "numDepartments": 1,
            "departments": [
                "GgYvrkAF63aeQmsh4"
            ],
            "_updatedAt": "2021-06-28T16:43:57.688Z"
        }
    ],
    "count": 1,
    "offset": 0,
    "total": 1,
    "success": true
}
```
