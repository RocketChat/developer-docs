# Get List of Unit Monitors

Provides a list of monitors for a unit

![](../../../../../../../.gitbook/assets/enterprise.jpg)

<table><thead><tr><th width="435.3333333333333">URL</th><th>Requires Auth</th><th>HTTP Method</th></tr></thead><tbody><tr><td><code>api/v1/livechat/units/:unitId/monitors</code></td><td><code>YES</code></td><td><code>GET</code></td></tr></tbody></table>

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/livechat/units/TGjc7wN84KxQup9cF/monitors' \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript
{
    "monitors": [
        {
            "_id": "Gv8rxcv4WTEDnnGiT",
            "monitorId": "MJk4XK5QpsFWJzmSz",
            "unitId": "TGjc7wN84KxQup9cF",
            "_updatedAt": "2022-11-21T11:16:01.708Z",
            "username": "jjay"
        },
        {
            "_id": "dvSh7G6WW6J5XykQw",
            "monitorId": "GdyoCfHfd3um5N9vP",
            "unitId": "TGjc7wN84KxQup9cF",
            "_updatedAt": "2022-11-21T11:16:01.718Z",
            "username": "j.coel"
        }
    ],
    "success": true
}
```
