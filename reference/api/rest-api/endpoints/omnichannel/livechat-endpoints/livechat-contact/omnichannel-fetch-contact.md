---
description: Retrieves a contact information.
---

# Fetch Omnichannel Contact

| URL                          | Requires Auth | HTTP Method |
| ---------------------------- | ------------- | ----------- |
| `api/v1/omnichannel/contact` | `YES`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Query Parameters

| Argument    | Example             | Required | Description |
| ----------- | ------------------- | -------- | ----------- |
| `contactId` | `mAm5YZHwHMrNj8fhu` | Required | Contact ID  |

## Example Call

```bash
curl --location --request GET http://localhost:3000/api/v1/omnichannel/contact?contactId=mAm5YZHwHMrNj8fhu \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript
{
    "contact": {
        "_id": "mAm5YZHwHMrNj8fhu",
        "username": "13034833887",
        "ts": "2021-07-07T13:04:38.079Z",
        "_updatedAt": "2021-07-07T13:04:38.452Z",
        "name": "Eduardo Pereira",
        "phone": [
            {
                "phoneNumber": "13034833887555193469973"
            }
        ],
        "token": "a90vrvv2r0lywsz1lr24x",
        "lastChat": {
            "_id": "67YQrd7secMv99WQ6",
            "ts": "2021-07-07T13:04:38.452Z"
        }
    },
    "success": true
}
```
