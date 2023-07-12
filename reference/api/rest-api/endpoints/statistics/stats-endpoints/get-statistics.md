# Get statistics

{% hint style="info" %}
Statistics about the Rocket.Chat server. Requires `view-statistics` permission.
{% endhint %}

| URL                 | Requires Auth | HTTP Method |
| ------------------- | ------------- | ----------- |
| `api/v1/statistics` | `YES`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Query Parameters

| Argument  | Example | Required | Description                    |
| --------- | ------- | -------- | ------------------------------ |
| `refresh` | `true`  | Optional | Need to refresh the statistics |

## Example Call

```bash
curl --location --request POST 'http://localhost:3000/api/v1/statistics\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

### Success

```javascript
{
  "_id":"wufRdmSrjmSMhBdTN",
  "uniqueId":"wD4EP3M7FeFzJZgk9",
  "installedAt":"2018-02-18T19:40:45.369Z",
  "version":"0.61.0-develop",
  "totalUsers":88,
  "activeUsers":88,
  "nonActiveUsers":0,
  "onlineUsers":0,
  "awayUsers":1,
  "offlineUsers":87,
  "totalRooms":81,
  "totalChannels":41,
  "totalPrivateGroups":37,
  "totalDirect":3,
  "totlalLivechat":0,
  "totalMessages":2408,
  "totalChannelMessages":730,
  "totalPrivateGroupMessages":1869,
  "totalDirectMessages":25,
  "totalLivechatMessages":0,
  "lastLogin":"2018-02-24T12:44:45.045Z",
  "lastMessageSentAt":"2018-02-23T18:14:03.490Z",
  "lastSeenSubscription":"2018-02-23T17:58:54.779Z",
  "os": {
    "type":"Linux",
    "platform":"linux",
    "arch":"x64",
    "release":"4.13.0-32-generic",
    "uptime":76242,
    "loadavg": [
      0.0576171875,0.04638671875,0.00439453125
    ],
    "totalmem":5787901952,
    "freemem":1151168512,
    "cpus": [
      {
        "model":"Intel(R) Xeon(R) CPU           E5620  @ 2.40GHz",
        "speed":2405,
        "times": {
          "user":6437000,
          "nice":586500,
          "sys":1432200,
          "idle":750117500,
          "irq":0
        }
      },
      {
        "model":"Intel(R) Xeon(R) CPU           E5620  @ 2.40GHz",
        "speed":2405,
        "times": {
          "user":7319700,
          "nice":268800,
          "sys":1823600,
          "idle":747642700,
          "irq":0
        }
      },
      {
        "model":"Intel(R) Xeon(R) CPU           E5620  @ 2.40GHz",
        "speed":2405,
        "times": {
          "user":7484600,
          "nice":1003500,
          "sys":1446000,
          "idle":748873400,
          "irq":0
        }
      },
      {
        "model":"Intel(R) Xeon(R) CPU           E5620  @ 2.40GHz",
        "speed":2405,
        "times": {
          "user":8378200,
          "nice":548500,
          "sys":1443200,
          "idle":747053300,
          "irq":0
        }
      }
    ]
  },
  "process": {
    "nodeVersion":"v8.9.4",
    "pid":11736,
    "uptime":16265.506
  },
  "deploy": {
    "method":"tar",
    "platform":"selfinstall"
  },
  "migration": {
    "_id":"control",
    "version":106,
    "locked":false,
    "lockedAt":"2018-02-23T18:13:13.948Z",
    "buildAt":"2018-02-18T17:22:51.212Z"
  },
  "instanceCount":1,
  "createdAt":"2018-02-24T13:13:00.236Z",
  "_updatedAt":"2018-02-24T13:13:00.236Z",
  "success":true
}
```

### Errors

The following error can occur upon the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.

{% tabs %}
{% tab title=" Authorization" %}
```javascript
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}
{% endtabs %}

## Change Log <a href="#change-log" id="change-log"></a>

| Version | Description |
| ------- | ----------- |
| 0.51.0  | Added       |
