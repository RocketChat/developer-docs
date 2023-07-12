---
description: Registers a guest user as a new omnichannel contact.
---

# Register or Update Omnichannel Contact

{% hint style="info" %}
To register a new contact, add a random unique string as the`token`parameter. To update a contact, use the existing`token`of that contact.
{% endhint %}

| URL                          | Requires Auth | HTTP Method |
| ---------------------------- | ------------- | ----------- |
| `api/v1/omnichannel/contact` | `YES`         | `POST`      |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Parameters

| Argument         | Example             | Required | Description            |
| ---------------- | ------------------- | -------- | ---------------------- |
| `token`          | `4WcmeBE4spXx6AxrC` | Required | Contact Token          |
| `name`           | `Chris`             | Required | Contact Name           |
| `email`          | `chris@gmail.com`   | Optional | Contact Email          |
| `phone`          | `+93334432224444`   | Optional | Contact Phone          |
| `contactManager` | `murtaza9`          | Optional | Conatac Manager's Name |

## Example Call

```bash
curl --location --request POST http://localhost:3000/api/v1/omnichannel/contact\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
-d {
"token" : "434lxd7iss8yh8c4m80wh",
"name" :  "Chris",
"email" : "chris@gmail.com",
"phone" : "+93334432224444",
"contactManager":{
      "username":"murtaza9"
   },
 }
```

## Result

```javascript
{
    "contact": "7ipCD6NDtkkRDCiNM",
    "success": true
}
```
