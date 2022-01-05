---
description: Registers a guest user as a new omnichannel contact.
---

# Register Omnichannel Contact

| URL                          | Requires Auth | HTTP Method |
| ---------------------------- | ------------- | ----------- |
| `api/v1/omnichannel/contact` | `YES`         | `POST`       |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Parameters

| Argument                                    | Example             | Required | Description   |
| ------------------------------------------- | ------------------- | -------- | ------------- |
| <p><code></code></p><p><code>_Id</code></p> | `7ipCD6NDtkkRDCiNM` | Required | Contact ID    |
| `token`                                     | `4WcmeBE4spXx6AxrC` | Required | Contact Token |
| `name`                                      | `Chris`             | Required | Contact Name  |
| `email`                                     | ` chris@gmail.com`  | Optional | Contact Email |
| `phone`                                     | `+93334432224444`   | Optional | Contact Phone |

## Example Call

```bash
curl --location --request POST http://localhost:3000/api/v1/omnichannel/contact\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
-d '{
"_id": "7ipCD6NDtkkRDCiNM",
"token" : "434lxd7iss8yh8c4m80wh",
"name" :  "Chris",
"email" : "chris@gmail.com",
"phone" : "+93334432224444"

 }'
```

## Result

```javascript
{
    "contact": "7ipCD6NDtkkRDCiNM",
    "success": true
}
```
