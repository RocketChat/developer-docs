---
description: Gives the details of a Priority
---

# Get one Priority

![](../../../../../../../../.gitbook/assets/enterprise.jpg)

{% hint style="info" %}
![](../../../../../../../../.gitbook/assets/Deprecated.png) This endpoint has been renamed to [get-a-priority.md](get-a-priority.md "mention") as from Rocket.Chat `5.0`
{% endhint %}

| URL                        | Requires Auth | HTTP Method |
| -------------------------- | ------------- | ----------- |
| `livechat/priority.getOne` | `YES`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Parameters

| Argument     | Example           | Required | Description |
| ------------ | ----------------- | -------- | ----------- |
| `priorityId` | 7Hu352k892rNh45j9 | Required | Priority ID |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/livechat/priorities.getOne?priorityId=7Hu352k892rNh45j9/
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript
{
    "_id": "7Hu352k892rNh45j9",
    "name": "Medium",
    "description": "Medium",
    "dueTimeInMinutes": 2,
    "_updatedAt": "2020-10-06T22:33:40.768Z",
    "success": true
}
```
