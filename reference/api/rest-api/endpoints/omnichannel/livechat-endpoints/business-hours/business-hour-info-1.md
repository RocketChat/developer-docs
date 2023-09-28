# Business Hour Info

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Fetches the default business hours of a workspace

{% hint style="info" %}
This requires the user making the call to have the `view-livechat-business-hours` permission
{% endhint %}

<table><thead><tr><th width="352.3333333333333">URL</th><th>Requires Auth</th><th>HTTP Method</th></tr></thead><tbody><tr><td><code>api/v1/livechat/business-hour</code></td><td><code>YES</code></td><td><code>GET</code></td></tr></tbody></table>

## Headers

| Argument       | Example                                    | Required | Description                                                    |
| -------------- | ------------------------------------------ | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `xnqTv4GAcaCBW6H33`                        | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `VJsIfdGCNrzxOW1sHf3r_ebe6mVGKfmzcwaEPqEt` | Required | Your token (returned after you log in through the API)         |

## Example Call

```bash


curl --location --request GET 'http://localhost:3000/api/v1/livechat/business-hour\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-id'
```

## Result

```json
{
    "businessHour": {
        "_id": "62f14dd55026d9aac120c653",
        "name": "",
        "active": true,
        "type": "default",
        "ts": "2022-08-08T17:54:29.441Z",
        "workHours": [
            {
                "day": "Monday",
                "start": {
                    "time": "08:00",
                    "utc": {
                        "dayOfWeek": "Monday",
                        "time": "08:00"
                    },
                    "cron": {
                        "dayOfWeek": "Monday",
                        "time": "08:00"
                    }
                },
                "finish": {
                    "time": "20:00",
                    "utc": {
                        "dayOfWeek": "Monday",
                        "time": "20:00"
                    },
                    "cron": {
                        "dayOfWeek": "Monday",
                        "time": "20:00"
                    }
                },
                "code": 1,
                "open": true
            },
            {
                "day": "Tuesday",
                "start": {
                    "time": "08:00",
                    "utc": {
                        "dayOfWeek": "Tuesday",
                        "time": "08:00"
                    },
                    "cron": {
                        "dayOfWeek": "Tuesday",
                        "time": "08:00"
                    }
                },
                "finish": {
                    "time": "20:00",
                    "utc": {
                        "dayOfWeek": "Tuesday",
                        "time": "20:00"
                    },
                    "cron": {
                        "dayOfWeek": "Tuesday",
                        "time": "20:00"
                    }
                },
                "code": 2,
                "open": true
            },
            {
                "day": "Wednesday",
                "start": {
                    "time": "08:00",
                    "utc": {
                        "dayOfWeek": "Wednesday",
                        "time": "08:00"
                    },
                    "cron": {
                        "dayOfWeek": "Wednesday",
                        "time": "08:00"
                    }
                },
                "finish": {
                    "time": "20:00",
                    "utc": {
                        "dayOfWeek": "Wednesday",
                        "time": "20:00"
                    },
                    "cron": {
                        "dayOfWeek": "Wednesday",
                        "time": "20:00"
                    }
                },
                "code": 3,
                "open": true
            },
            {
                "day": "Thursday",
                "start": {
                    "time": "08:00",
                    "utc": {
                        "dayOfWeek": "Thursday",
                        "time": "08:00"
                    },
                    "cron": {
                        "dayOfWeek": "Thursday",
                        "time": "08:00"
                    }
                },
                "finish": {
                    "time": "20:00",
                    "utc": {
                        "dayOfWeek": "Thursday",
                        "time": "20:00"
                    },
                    "cron": {
                        "dayOfWeek": "Thursday",
                        "time": "20:00"
                    }
                },
                "code": 4,
                "open": true
            },
            {
                "day": "Friday",
                "start": {
                    "time": "08:00",
                    "utc": {
                        "dayOfWeek": "Friday",
                        "time": "08:00"
                    },
                    "cron": {
                        "dayOfWeek": "Friday",
                        "time": "08:00"
                    }
                },
                "finish": {
                    "time": "20:00",
                    "utc": {
                        "dayOfWeek": "Friday",
                        "time": "20:00"
                    },
                    "cron": {
                        "dayOfWeek": "Friday",
                        "time": "20:00"
                    }
                },
                "code": 5,
                "open": true
            },
            {
                "day": "Saturday",
                "start": {
                    "time": "08:00",
                    "utc": {
                        "dayOfWeek": "Saturday",
                        "time": "08:00"
                    },
                    "cron": {
                        "dayOfWeek": "Saturday",
                        "time": "08:00"
                    }
                },
                "finish": {
                    "time": "20:00",
                    "utc": {
                        "dayOfWeek": "Saturday",
                        "time": "20:00"
                    },
                    "cron": {
                        "dayOfWeek": "Saturday",
                        "time": "20:00"
                    }
                },
                "code": 6,
                "open": false
            },
            {
                "day": "Sunday",
                "start": {
                    "time": "08:00",
                    "utc": {
                        "dayOfWeek": "Sunday",
                        "time": "08:00"
                    },
                    "cron": {
                        "dayOfWeek": "Sunday",
                        "time": "08:00"
                    }
                },
                "finish": {
                    "time": "20:00",
                    "utc": {
                        "dayOfWeek": "Sunday",
                        "time": "20:00"
                    },
                    "cron": {
                        "dayOfWeek": "Sunday",
                        "time": "20:00"
                    }
                },
                "code": 7,
                "open": false
            }
        ],
        "timezone": {
            "name": "Africa/Abidjan",
            "utc": "0"
        },
        "_updatedAt": "2023-01-02T18:30:31.632Z"
    },
    "success": true
}s
```
