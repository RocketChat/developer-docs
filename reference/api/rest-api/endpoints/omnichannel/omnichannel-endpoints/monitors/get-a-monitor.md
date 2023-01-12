# Get a Monitor

![](../../../../../../../.gitbook/assets/enterprise.jpg)

| URL                                  | Requires Auth | HTTP Method |
| ------------------------------------ | ------------- | ----------- |
| `api/v1/livechat/monitors/:username` | `YES`         | `GET`       |

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
