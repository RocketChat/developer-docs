# Get a Monitor

![](../../../../../../../.gitbook/assets/enterprise.jpg)

<table><thead><tr><th width="404.3333333333333">URL</th><th>Requires Auth</th><th>HTTP Method</th></tr></thead><tbody><tr><td><code>api/v1/livechat/monitors/:username</code></td><td><code>YES</code></td><td><code>GET</code></td></tr></tbody></table>

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Path Parameters

| Argument   | Example   | Required | Description                           |
| ---------- | --------- | -------- | ------------------------------------- |
| `username` | `1-agent` | Required | The username of the person monitoring |

## Example Call

```bash


curl --location --request GET 'http://localhost:3000/api/v1/livechat/monitors/1-agent' \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript
{
    "_id": "RSb7exHJsiKqwRjPF",
    "username": "1-agent",
    "emails": [
        {
            "address": "1-agent@g.c",
            "verified": false
        }
    ],
    "status": "offline",
    "name": "1-agent",
    "statusLivechat": "not-available",
    "livechat": {
        "maxNumberSimultaneousChat": "-4"
    },
    "success": true
}
```
