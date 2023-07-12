---
description: Create a unit
---

# Create Unit

​​

<figure><img src="https://files.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWf1K8RJU-TjNEtPxvb%2F-MdYMamkk8ovpBMXvbHS%2F-MdYNoNP9yQ4DY7S9i37%2FEnterprise.jpg?alt=media&#x26;token=181a0d13-d261-4a6e-b4b2-ded19b2d5e32" alt=""><figcaption></figcaption></figure>

| URL                     | Requires Auth | HTTP Method |
| ----------------------- | ------------- | ----------- |
| `api/v1/livechat/units` | `YES`         | `POST`      |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Payload

| Argument          | Example                                                          | Required | Description                  |
| ----------------- | ---------------------------------------------------------------- | -------- | ---------------------------- |
| `unitData`        | `{ "name": "unitxx2", "visibility": "public" }`                  | Optional | Data of the unit             |
| `unitMonitors`    | `[{ "monitorId": "GT67Tv6x5p5y5xZWN", "username": "testerio" }]` | Optional | Information on unit monitors |
| `unitDepartments` | `[{ "departmentId": "CgM4vfNNtj8t4QEMd" }]`                      | Optional | Unit department              |

## Example Call

```bash
curl --location --request POST 'localhost:3000/api/v1/livechat/units' \
--header 'x-Auth-token: jx-CrbeqbxPimsZr1UAhO3NsJdU8yB0MVoXkGOKQ3xL' \
--header 'x-user-id: 6vHSSqdBHdm2R4gfi' \
--header 'Content-Type: application/json' \
--data-raw '{
	"unitData": {
        "name": "unitxx2",
        "visibility": "public"
    },
    "unitMonitors": [{
        "monitorId": "GT67Tv6x5p5y5xZWN",
        "username": "testerio"
    }],
    "unitDepartments": [{
        "departmentId": "CgM4vfNNtj8t4QEMd"
    }]
}
'
```

## Results

```
{
    "name": "unitxx2",
    "visibility": "public",
    "type": "u",
    "numMonitors": 1,
    "numDepartments": 1,
    "_updatedAt": "2021-12-06T14:30:27.744Z",
    "_id": "o5zNtKy7BcTMgyXtm"
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| `4.2.0` | Added       |
