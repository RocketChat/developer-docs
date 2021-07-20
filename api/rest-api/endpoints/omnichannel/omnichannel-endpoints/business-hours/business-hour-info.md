---
description: Retrieves all the information of a particular business hour.
---

# Business Hour Info



| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `api/v1/livechat/business-hour` | `YES` | `GET` |

## Headers

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `X-User-Id` | `myuser-name` | Required | Your username hash \(returned after you log in through the API\) |
| `X-Auth-Token` | `myauth-token` | Required | Your token \(returned after you log in through the API\) |

##  Parameters

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `_Id` | `5f071f83a05d58ba2cd8b046` | Required | Business Hour ID |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/livechat/business-hour?_id=5f071f83a05d58ba2cd8b046 \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript
{
    "businessHour": {
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
                        "time": "03:00"
                    },
                    "cron": {
                        "dayOfWeek": "Monday",
                        "time": "03:00"
                    }
                },
                "finish": {
                    "time": "23:00",
                    "utc": {
                        "dayOfWeek": "Monday",
                        "time": "20:00"
                    },
                    "cron": {
                        "dayOfWeek": "Monday",
                        "time": "20:00"
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
                        "time": "03:00"
                    },
                    "cron": {
                        "dayOfWeek": "Tuesday",
                        "time": "03:00"
                    }
                },
                "finish": {
                    "time": "21:00",
                    "utc": {
                        "dayOfWeek": "Tuesday",
                        "time": "18:00"
                    },
                    "cron": {
                        "dayOfWeek": "Tuesday",
                        "time": "18:00"
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
                        "time": "03:00"
                    },
                    "cron": {
                        "dayOfWeek": "Wednesday",
                        "time": "03:00"
                    }
                },
                "finish": {
                    "time": "22:00",
                    "utc": {
                        "dayOfWeek": "Wednesday",
                        "time": "19:00"
                    },
                    "cron": {
                        "dayOfWeek": "Wednesday",
                        "time": "19:00"
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
                        "time": "03:00"
                    },
                    "cron": {
                        "dayOfWeek": "Thursday",
                        "time": "03:00"
                    }
                },
                "finish": {
                    "time": "21:00",
                    "utc": {
                        "dayOfWeek": "Thursday",
                        "time": "18:00"
                    },
                    "cron": {
                        "dayOfWeek": "Thursday",
                        "time": "18:00"
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
                        "time": "03:00"
                    },
                    "cron": {
                        "dayOfWeek": "Friday",
                        "time": "03:00"
                    }
                },
                "finish": {
                    "time": "21:00",
                    "utc": {
                        "dayOfWeek": "Friday",
                        "time": "18:00"
                    },
                    "cron": {
                        "dayOfWeek": "Friday",
                        "time": "18:00"
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
                        "time": "05:00"
                    },
                    "cron": {
                        "dayOfWeek": "Saturday",
                        "time": "05:00"
                    }
                },
                "finish": {
                    "time": "20:00",
                    "utc": {
                        "dayOfWeek": "Saturday",
                        "time": "17:00"
                    },
                    "cron": {
                        "dayOfWeek": "Saturday",
                        "time": "17:00"
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
                        "time": "05:00"
                    },
                    "cron": {
                        "dayOfWeek": "Sunday",
                        "time": "05:00"
                    }
                },
                "finish": {
                    "time": "20:00",
                    "utc": {
                        "dayOfWeek": "Sunday",
                        "time": "17:00"
                    },
                    "cron": {
                        "dayOfWeek": "Sunday",
                        "time": "17:00"
                    }
                },
                "open": false
            }
        ],
        "timezone": {
            "name": "Asia/Aden",
            "utc": "+03:00"
        },
        "departmentsToApplyBusinessHour": "",
        "_updatedAt": "2021-07-19T10:27:33.745Z"
    },
    "success": true
}
```

