---
description: Delete a unit
---

# Delete Unit

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

| URL                         | Requires Auth | HTTP Method |
| --------------------------- | ------------- | ----------- |
| `api/v1/livechat/units/:id` | `YES`         | `DELETE`    |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Path Variable

| Argument | Example             | Required | Description |
| -------- | ------------------- | -------- | ----------- |
| `id`     | `oPK7Z735JdTuMZXmQ` | Required | The unit id |

## Example Call

```bash
curl --location --request DELETE 'localhost:3000/api/v1/livechat/units/oPK7Z735JdTuMZXmQ' \
--header 'x-Auth-token: jx-CrbeqbxPimsZr1UAhO3NsJdU8yB0MVoXkGOKQ3xL' \
--header 'x-user-id: 6vHSSqdBHdm2R4gfi'
```

## Results

### Success

```
{
 "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| `4.2.0` | Added       |
