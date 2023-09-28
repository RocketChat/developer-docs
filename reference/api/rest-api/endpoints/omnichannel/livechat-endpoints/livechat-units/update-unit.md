# Update Unit

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

| URL                         | Requires Auth | HTTP Method |
| --------------------------- | ------------- | ----------- |
| `api/v1/livechat/units/:id` | `YES`         | `POST`      |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Path Variable

| Argument | Example             | Required | Description |
| -------- | ------------------- | -------- | ----------- |
| `id`     | `4uErt483aPJAg6Xk4` | Required | The unit id |

## Payload

| Argument          | Example                                                          | Required | Description                  |
| ----------------- | ---------------------------------------------------------------- | -------- | ---------------------------- |
| `unitData`        | `{ "name": "unitxx2", "visibility": "private" }`                 | Optional | Data of the unit             |
| `unitMonitors`    | `[{ "monitorId": "GT67Tv6x5p5y5xZWN", "username": "testerio" }]` | Optional | Information on unit monitors |
| `unitDepartments` | `[{ "departmentId": "CgM4vfNNtj8t4QEMd" }]`                      | Optional | Unit department              |

## Example Call

```
curl --location --request POST 'localhost:3000/api/v1/livechat/units/4uErt483aPJAg6Xk4' \
--header 'x-Auth-token: jx-CrbeqbxPimsZr1UAhO3NsJdU8yB0MVoXkGOKQ3xL' \
--header 'x-user-id: 6vHSSqdBHdm2R4gfi' \
--header 'Content-Type: application/json' \
--data-raw '{
	"unitData": {
        "name": "unitxx2",
        "visibility": "private"
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
    "visibility": "private",
    "type": "u",
    "numMonitors": 1,
    "numDepartments": 1,
    "_updatedAt": "2021-12-06T14:40:59.478Z",
    "_id": "o5zNtKy7BcTMgyXtm"
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| `4.2.0` | Added       |
