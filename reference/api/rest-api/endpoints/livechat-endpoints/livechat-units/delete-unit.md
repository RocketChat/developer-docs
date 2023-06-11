---
description: Delete a unit
---

# Delete Unit

​​![](https://files.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWf1K8RJU-TjNEtPxvb%2F-MdYMamkk8ovpBMXvbHS%2F-MdYNoNP9yQ4DY7S9i37%2FEnterprise.jpg?alt=media\&token=181a0d13-d261-4a6e-b4b2-ded19b2d5e32)

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
