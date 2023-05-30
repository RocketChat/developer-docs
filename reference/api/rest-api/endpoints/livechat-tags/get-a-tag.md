---
description: Get the details of a tag
---

# Get a Tag

<figure><img src="https://2858450009-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWf1K8RJU-TjNEtPxvb%2Fuploads%2Fgit-blob-1654b99a4e9df54521f42da4d3c1a7fbdb9f2238%2FEnterprise.jpg?alt=media" alt=""><figcaption></figcaption></figure>

| URL                    | Requires Auth | HTTP Method |
| ---------------------- | ------------- | ----------- |
| `livechat/tags/:tagId` | `YES`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Path Variable

| Argument | Example             | Required | Description |
| -------- | ------------------- | -------- | ----------- |
| `tagId`  | `pXkCRLGxD34y2FEZq` | Required | Tag ID      |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/livechat/tags/:tagId\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript
{
    "_id": "nNJntq2n6GBdR8JC4",
    "name": "331",
    "numDepartments": 2,
    "departments": [
        "kxL4qaa29SMpy3ZXG",
        "WRY3EFGAT9Xh5NFBv"
    ],
    "_updatedAt": "2022-11-28T07:17:31.973Z",
    "description": "xfgh",
    "success": true
}
```
