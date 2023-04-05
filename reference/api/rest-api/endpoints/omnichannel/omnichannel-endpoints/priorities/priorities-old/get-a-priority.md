---
description: Get the details of a priority
---

# Get a Priority

<figure><img src="../../../../../../../../.gitbook/assets/enterprise.jpg" alt=""><figcaption></figcaption></figure>

| URL                               | Requires Auth | HTTP Method |
| --------------------------------- | ------------- | ----------- |
| `livechat/priorities/:priorityId` | `YES`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Path Variables

| Argument     | Example           | Required | Description |
| ------------ | ----------------- | -------- | ----------- |
| `priorityId` | 7Hu352k892rNh45j9 | Required | Priority ID |

## Example Call

```bash
    curl --location --request GET 'http://localhost:3000/api/v1/livechat/priorities/:priorityId
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript
{
    "_id": "idQkJgzTND3gBRNWJ",
    "name": "low",
    "description": "test",
    "dueTimeInMinutes": 2,
    "_updatedAt": "2022-10-04T13:48:07.371Z",
    "success": true
}
```
