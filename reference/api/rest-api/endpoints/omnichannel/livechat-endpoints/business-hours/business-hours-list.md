---
description: Gives a list of existing business hours
---

# Business Hours List

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
![](../../../../../../../.gitbook/assets/Deprecated.png) This endpoint has been renamed to [get-business-hours.md](get-business-hours.md "mention") from Rocket.Chat `5.0`
{% endhint %}

<table><thead><tr><th width="163">HTTP Method</th><th width="305">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/business-hours.list</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request GET 'http://localhost:3000/api/v1/livechat/business-hours.list\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```
{% endcode %}

## Example Response

```javascript
{
    "businessHours": [
        {
            "_id": "5f071f83a05d58ba2cd8b046",
            "ts": "2020-07-09T13:45:39.633Z",
            "name": "",
            "active": true,
            "type": "default",
            "workHours": [
                {
                    "day": "Monday",
                    "start": {
                        "time": "06:00",
                        "utc": {
                            "dayOfWeek": "Monday",
                            "time": "09:00"
                        },
                        "cron": {
                            "dayOfWeek": "Monday",
                            "time": "09:00"
                        }
                    },
                    "finish": {
                        "time": "22:00",
                        "utc": {
                            "dayOfWeek": "Tuesday",
                            "time": "01:00"
                        },
                        "cron": {
                            "dayOfWeek": "Tuesday",
                            "time": "01:00"
                        }
                    },
                    "open": true
                },
                {
                    "day": "Tuesday",
                    "start": {
                        "time": "06:00",
                        "utc": {
                            "dayOfWeek": "Tuesday",
                            "time": "09:00"
                        },
                        "cron": {
                            "dayOfWeek": "Tuesday",
                            "time": "09:00"
                        }
                    },
                    "finish": {
                        "time": "21:00",
                        "utc": {
                            "dayOfWeek": "Wednesday",
                            "time": "00:00"
                        },
                        "cron": {
                            "dayOfWeek": "Wednesday",
                            "time": "00:00"
                        }
                    },
                    "open": true
                },
                {
                    "day": "Wednesday",
                    "start": {
                        "time": "06:00",
                        "utc": {
                            "dayOfWeek": "Wednesday",
                            "time": "09:00"
                        },
                        "cron": {
                            "dayOfWeek": "Wednesday",
                            "time": "09:00"
                        }
                    },
                    "finish": {
                        "time": "22:00",
                        "utc": {
                            "dayOfWeek": "Thursday",
                            "time": "01:00"
                        },
                        "cron": {
                            "dayOfWeek": "Thursday",
                            "time": "01:00"
                        }
                    },
                    "open": true
                },
                {
                    "day": "Thursday",
                    "start": {
                        "time": "06:00",
                        "utc": {
                            "dayOfWeek": "Thursday",
                            "time": "09:00"
                        },
                        "cron": {
                            "dayOfWeek": "Thursday",
                            "time": "09:00"
                        }
                    },
                    "finish": {
                        "time": "21:00",
                        "utc": {
                            "dayOfWeek": "Friday",
                            "time": "00:00"
                        },
                        "cron": {
                            "dayOfWeek": "Friday",
                            "time": "00:00"
                        }
                    },
                    "open": true
                },
                {
                    "day": "Friday",
                    "start": {
                        "time": "06:00",
                        "utc": {
                            "dayOfWeek": "Friday",
                            "time": "09:00"
                        },
                        "cron": {
                            "dayOfWeek": "Friday",
                            "time": "09:00"
                        }
                    },
                    "finish": {
                        "time": "21:00",
                        "utc": {
                            "dayOfWeek": "Saturday",
                            "time": "00:00"
                        },
                        "cron": {
                            "dayOfWeek": "Saturday",
                            "time": "00:00"
                        }
                    },
                    "open": true
                },
                {
                    "day": "Saturday",
                    "start": {
                        "time": "08:00",
                        "utc": {
                            "dayOfWeek": "Saturday",
                            "time": "11:00"
                        },
                        "cron": {
                            "dayOfWeek": "Saturday",
                            "time": "11:00"
                        }
                    },
                    "finish": {
                        "time": "20:00",
                        "utc": {
                            "dayOfWeek": "Saturday",
                            "time": "23:00"
                        },
                        "cron": {
                            "dayOfWeek": "Saturday",
                            "time": "23:00"
                        }
                    },
                    "open": false
                },
                {
                    "day": "Sunday",
                    "start": {
                        "time": "08:00",
                        "utc": {
                            "dayOfWeek": "Sunday",
                            "time": "11:00"
                        },
                        "cron": {
                            "dayOfWeek": "Sunday",
                            "time": "11:00"
                        }
                    },
                    "finish": {
                        "time": "20:00",
                        "utc": {
                            "dayOfWeek": "Sunday",
                            "time": "23:00"
                        },
                        "cron": {
                            "dayOfWeek": "Sunday",
                            "time": "23:00"
                        }
                    },
                    "open": false
                }
            ],
            "timezone": {
                "name": "America/Sao_Paulo",
                "utc": "-03:00"
            },
            "departmentsToApplyBusinessHour": ""
        }
    ],
    "count": 1,
    "offset": 0,
    "total": 1,
    "success": true
}
```
