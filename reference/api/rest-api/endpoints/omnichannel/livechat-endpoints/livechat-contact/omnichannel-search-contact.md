---
description: Search a contact information.
---

# Omnichannel Search Contact

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `api/v1/omnichannel/contact.search` | `YES` | `GET` |

## Headers

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `X-User-Id` | `myuser-name` | Required | Your username hash \(returned after you log in through the API\) |
| `X-Auth-Token` | `myauth-token` | Required | Your token \(returned after you log in through the API\) |

## Query Parameters

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `email` | `edu@gmail.com` | Required | Contact email address |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/omnichannel/contact?contactId=mAm5YZHwHMrNj8fhu \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

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

