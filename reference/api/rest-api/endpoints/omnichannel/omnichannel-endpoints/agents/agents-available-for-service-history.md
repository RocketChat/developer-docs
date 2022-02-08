---
description: Return the list of agents and their available time for the provided time frame
---

# Agents available for service history

![](../../../../../../../.gitbook/assets/enterprise.jpg)

| URL                                                              | Requires Auth | HTTP Method |
| ---------------------------------------------------------------- | ------------- | ----------- |
| `api/v1/livechat/analytics/agents/available-for-service-history` | `YES`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Parameters

| Argument | Example                    | Required | Description |
| -------- | -------------------------- | -------- | ----------- |
| `start`  | `2020-09-09T00:11:22.345Z` | Required | start date  |
| `end`    | `2020-09-10T23:59:22.345Z` | Required | end date    |
| `fullReport`    | `true` | Optional | If set to "true", then it will share the service history which will contain more granular data like about what time of the day agent was available |

### Notes

* \*\* The API will return a blank page if the correct headers are not sent

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/livechat/analytics/agents/available-for-service-history?start=2020-09-09T00:11:22.345Z&end=2020-09-10T23:59:22.345Z' \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

Result without `fullReport` flag set to true. It will only return a high level consolidated data about total available time, per agent within the specified duration

```javascript
{
    "agents": [
        {
            "availableTimeInSeconds": 102117,
            "username": "andres.mauricio"
        },
        {
            "availableTimeInSeconds": 280,
            "username": "bruna.martins"
        },
        {
            "availableTimeInSeconds": 40242,
            "username": "marina"
        },
        {
            "availableTimeInSeconds": 1,
            "username": "rogerio"
        }
    ],
    "count": 4,
    "offset": 0,
    "total": 4,
    "success": true
}
```


Result with `fullReport` flag set to true. Note: It will contain an extra property "serviceHistory".


```javascript
{
    "agents": [
        {
            "serviceHistory": [
                {
                    "startedAt": "2021-11-24T08:35:49.058Z",
                    "stoppedAt": "2021-11-24T08:41:32.721Z"
                },
                {
                    "startedAt": "2021-11-24T08:51:15.623Z",
                    "stoppedAt": "2021-11-24T08:53:59.707Z"
                },
                {
                    "startedAt": "2021-11-24T08:55:45.128Z",
                    "stoppedAt": "2021-11-24T08:55:45.214Z"
                },
                {
                    "startedAt": "2021-11-24T16:56:35.486Z",
                    "stoppedAt": "2021-11-24T17:05:56.611Z"
                },
                {
                    "startedAt": "2021-11-24T17:20:26.066Z",
                    "stoppedAt": "2021-11-24T18:29:59.000Z"
                }
            ],
            "availableTimeInSeconds": 2115334,
            "username": "murtaza98"
        },
        {
            "serviceHistory": [
                {
                    "startedAt": "2022-02-06T09:45:26.476Z",
                    "stoppedAt": "2022-02-06T09:45:27.499Z"
                },
                {
                    "startedAt": "2022-02-06T09:45:28.083Z",
                    "stoppedAt": "2022-02-06T09:45:28.663Z"
                },
                {
                    "startedAt": "2022-02-06T09:45:29.117Z",
                    "stoppedAt": "2022-02-06T09:45:29.672Z"
                },
                {
                    "startedAt": "2022-02-06T09:45:30.129Z",
                    "stoppedAt": "2022-02-06T09:45:30.534Z"
                },
                {
                    "startedAt": "2022-02-06T09:45:30.923Z",
                    "stoppedAt": "2022-02-06T09:45:31.714Z"
                },
                {
                    "startedAt": "2022-02-06T09:45:39.037Z",
                    "stoppedAt": "2022-02-06T09:45:41.680Z"
                }
            ],
            "availableTimeInSeconds": 7586,
            "username": "john"
        },
        {
            "serviceHistory": [
                {
                    "startedAt": "2021-12-27T13:25:44.459Z",
                    "stoppedAt": "2021-12-27T13:27:11.208Z"
                }
            ],
            "availableTimeInSeconds": 1508,
            "username": "max"
        }
    ],
    "count": 6,
    "offset": 0,
    "total": 6,
    "success": true
}
```


## Change Log
