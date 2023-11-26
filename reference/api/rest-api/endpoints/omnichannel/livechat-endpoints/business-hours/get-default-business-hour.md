# Get Default Business Hour

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Fetches the default business hours of a workspace.

<table><thead><tr><th width="163">HTTP Method</th><th width="305">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/business-hour</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `view-livechat-business-hours`
{% endhint %}

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request GET 'http://localhost:3000/api/v1/livechat/business-hour\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-id'
```
{% endcode %}

## Example Response

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
}
```
