---
description: >-
  Use this endpoint to find contacts by name, email, phone number or any custom
  field values stored in the database.
---

# Omnichannel Search Contact

| URL                                 | Requires Auth | HTTP Method |
| ----------------------------------- | ------------- | ----------- |
| `api/v1/omnichannel/contact.search` | `YES`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Query Parameters

| Argument | Example           | Required | Description                         |
| -------- | ----------------- | -------- | ----------------------------------- |
| `email`  | `edu@gmail.com`   | Optional | Search contacts by Co email address |
| `phone`  | `+13034833887`    | Optional | Contact phone number                |
| `custom` | `fieldName=value` | Optional | Contact custom field                |

## Example Call

### Find contacts by Email ID&#x20;

```bash
curl --location --request GET http://localhost:3000/api/v1/omnichannel/contact?email=edu@gmail.com \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

### Find contacts by Phone Number&#x20;

```
curl --location --request GET http://localhost:3000/api/v1/omnichannel/contact?phone=111111111 \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

### Find Contacts through Custom Fields

```
curl --location --request GET http://localhost:3000/api/v1/omnichannel/contact?custom=field_name%3Dfield_value \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

The `custom` query parameter can be used to search for a contact by a custom field. The `custom` query parameter must be encoded by [URLSearchParams](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams).

## Result

```javascript
{
    "contact": {
        "_id": "pp4aRWgsFdYorJXkw",
        "username": "13034833887",
        "ts": "2021-03-24T01:35:37.561Z",
        "_updatedAt": "2021-06-15T19:49:36.589Z",
        "phone": [
            {
                "phoneNumber": "whatsapp:+13034833887"
            }
        ],
        "token": "c4az7YPy667xxJ7Ny",
        "lastChat": {
            "_id": "fG6XvqSWxhwP64g4M",
            "ts": "2021-06-15T19:48:49.481Z"
        },
        "department": "GgYvrkAF63aeQmsh4",
        "contactManager": null,
        "livechatData": {},
        "name": "Edu Pereira",
        "visitorEmails": [
            {
                "address": ""
            }
        ]
    },
    "success": true
}
```
