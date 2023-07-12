---
description: Sets the priority of an inquiry
---

# Inquiry Prioritize

![](../../../../../../../.gitbook/assets/enterprise.jpg)

{% hint style="info" %}
An incoming chat, that has not yet been taken by the agent is called an 'inquiry'. After it's been taken by the agent it is referred to as 'room'.
{% endhint %}

| URL                                  | Requires Auth | HTTP Method |
| ------------------------------------ | ------------- | ----------- |
| `api/v1/livechat/inquiry.prioritize` | `YES`         | `PUT`       |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Parameters

| Argument   | Example             | Required | Description |
| ---------- | ------------------- | -------- | ----------- |
| `roomId`   | `Ey3RanxiR4wDCdWqy` | Required | Inquiry     |
| `priority` | `4WcmeBE4spXx6AxrC` | Required | Priority ID |

{% hint style="info" %}
`roomID` is actually `inquiry`. It the ID of the chat that's not been taken yet by the agent.
{% endhint %}

## Example Call

```bash
curl --location --request PUT 'http://localhost:3000/api/v1/livechat/inquiry.prioritize'\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
-d '{ "roomId": "Ey3RanxiR4wDCdWqy", "priority": "4WcmeBE4spXx6AxrC" }'
```

## Result

```javascript
{
    "success": true
}
```
