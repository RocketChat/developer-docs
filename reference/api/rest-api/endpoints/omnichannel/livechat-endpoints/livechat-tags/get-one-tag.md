---
description: Gives the details of a tag
---

# Get one Tag

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
<img src="../../../../../../../.gitbook/assets/Deprecated.png" alt="" data-size="line"> This endpoint has been renamed to [get-a-tag.md](get-a-tag.md "mention") as from Rocket.Chat `5.0`
{% endhint %}

| URL                    | Requires Auth | HTTP Method |
| ---------------------- | ------------- | ----------- |
| `livechat/tags.getOne` | `YES`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Parameters

| Argument | Example             | Required | Description |
| -------- | ------------------- | -------- | ----------- |
| `tagId`  | `pXkCRLGxD34y2FEZq` | Required | Tag ID      |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/livechat/tags.getOne?tagId=pXkCRLGxD34y2FEZq\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript
{
    "_id": "pXkCRLGxD34y2FEZq",
    "name": "Valuable  lead",
    "description": "high chances of conversion",
    "numDepartments": 1,
    "departments": [
        "GgYvrkAF63aeQmsh4"
    ],
    "_updatedAt": "2021-06-28T16:43:57.688Z",
    "success": true
}
```
