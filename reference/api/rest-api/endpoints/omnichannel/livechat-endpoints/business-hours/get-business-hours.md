# Get Business Hours

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Retrieves all the business hours attached to a workspace.

<table><thead><tr><th width="163">HTTP Method</th><th width="305">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/business-hours</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `view-livechat-business-hours`
{% endhint %}

## Query Parameters

This endpoint supports the optional [#pagination](../../../../#pagination "mention")query parameters. Additional optional parameters are as follows:

<table><thead><tr><th width="168">Key</th><th width="280">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>name</code></td><td><code>indian support time</code></td><td>Name of the business hour.</td></tr></tbody></table>

## Example Call

{% tabs %}
{% tab title="General call" %}
{% code overflow="wrap" %}
```powershell
curl --location --request GET 'http://localhost:3000/api/v1/livechat/business-hours'\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-id'
```
{% endcode %}
{% endtab %}

{% tab title="Call with name parameter" %}
{% code overflow="wrap" %}
```powershell
curl --location --request GET 'http://localhost:3000/api/v1/livechat/business-hours?name=indian support time ' \
--header 'X-User-Id:  myauth-token' \
--header 'X-Auth-Token: myuser-id'
```
{% endcode %}
{% endtab %}
{% endtabs %}

## Example Response

{% tabs %}
{% tab title="General Response" %}
```json
{
    "businessHours": [
        {
            "_id": "5eeed2c5ffea9759d3a0e5ac",
            "name": "",
            "active": true,
            "type": "default",
            "ts": "2020-06-21T03:24:02.252Z",
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
                        "time": "21:06",
                        "utc": {
                            "dayOfWeek": "Monday",
                            "time": "21:06"
                        },
                        "cron": {
                            "dayOfWeek": "Monday",
                            "time": "21:06"
                        }
                    },
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
                        "time": "10:00",
                        "utc": {
                            "dayOfWeek": "Tuesday",
                            "time": "10:00"
                        },
                        "cron": {
                            "dayOfWeek": "Tuesday",
                            "time": "10:00"
                        }
                    },
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
                        "time": "21:00",
                        "utc": {
                            "dayOfWeek": "Wednesday",
                            "time": "21:00"
                        },
                        "cron": {
                            "dayOfWeek": "Wednesday",
                            "time": "21:00"
                        }
                    },
                    "open": true
                },
                {
                    "day": "Thursday",
                    "start": {
                        "time": "01:00",
                        "utc": {
                            "dayOfWeek": "Thursday",
                            "time": "01:00"
                        },
                        "cron": {
                            "dayOfWeek": "Thursday",
                            "time": "01:00"
                        }
                    },
                    "finish": {
                        "time": "23:00",
                        "utc": {
                            "dayOfWeek": "Thursday",
                            "time": "23:00"
                        },
                        "cron": {
                            "dayOfWeek": "Thursday",
                            "time": "23:00"
                        }
                    },
                    "open": true
                },
                {
                    "day": "Friday",
                    "start": {
                        "time": "10:00",
                        "utc": {
                            "dayOfWeek": "Friday",
                            "time": "10:00"
                        },
                        "cron": {
                            "dayOfWeek": "Friday",
                            "time": "10:00"
                        }
                    },
                    "finish": {
                        "time": "22:00",
                        "utc": {
                            "dayOfWeek": "Friday",
                            "time": "22:00"
                        },
                        "cron": {
                            "dayOfWeek": "Friday",
                            "time": "22:00"
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
                    "open": false
                }
            ],
            "timezone": {
                "name": "Africa/Abidjan",
                "utc": "0"
            },
            "_updatedAt": "2022-12-05T17:12:11.585Z",
            "departmentsToApplyBusinessHour": ""
        },
        {
            "_id": "62b1f74aa98c5b539adc912c",
            "ts": "2022-06-21T16:52:26.386Z",
            "name": "indian support time ",
            "workHours": [
                {
                    "day": "Monday",
                    "start": {
                        "time": "10:00",
                        "utc": {
                            "dayOfWeek": "Monday",
                            "time": "04:30"
                        },
                        "cron": {
                            "dayOfWeek": "Monday",
                            "time": "04:30"
                        }
                    },
                    "finish": {
                        "time": "12:00",
                        "utc": {
                            "dayOfWeek": "Monday",
                            "time": "06:30"
                        },
                        "cron": {
                            "dayOfWeek": "Monday",
                            "time": "06:30"
                        }
                    },
                    "open": true
                },
                {
                    "day": "Tuesday",
                    "start": {
                        "time": "00:00",
                        "utc": {
                            "dayOfWeek": "Monday",
                            "time": "18:30"
                        },
                        "cron": {
                            "dayOfWeek": "Monday",
                            "time": "18:30"
                        }
                    },
                    "finish": {
                        "time": "23:00",
                        "utc": {
                            "dayOfWeek": "Tuesday",
                            "time": "17:30"
                        },
                        "cron": {
                            "dayOfWeek": "Tuesday",
                            "time": "17:30"
                        }
                    },
                    "open": true
                },
                {
                    "day": "Wednesday",
                    "start": {
                        "time": "08:00",
                        "utc": {
                            "dayOfWeek": "Wednesday",
                            "time": "02:30"
                        },
                        "cron": {
                            "dayOfWeek": "Wednesday",
                            "time": "02:30"
                        }
                    },
                    "finish": {
                        "time": "23:00",
                        "utc": {
                            "dayOfWeek": "Wednesday",
                            "time": "17:30"
                        },
                        "cron": {
                            "dayOfWeek": "Wednesday",
                            "time": "17:30"
                        }
                    },
                    "open": true
                },
                {
                    "day": "Thursday",
                    "start": {
                        "time": "10:00",
                        "utc": {
                            "dayOfWeek": "Thursday",
                            "time": "04:30"
                        },
                        "cron": {
                            "dayOfWeek": "Thursday",
                            "time": "04:30"
                        }
                    },
                    "finish": {
                        "time": "01:00",
                        "utc": {
                            "dayOfWeek": "Wednesday",
                            "time": "19:30"
                        },
                        "cron": {
                            "dayOfWeek": "Wednesday",
                            "time": "19:30"
                        }
                    },
                    "open": true
                },
                {
                    "day": "Friday",
                    "start": {
                        "time": "12:00",
                        "utc": {
                            "dayOfWeek": "Friday",
                            "time": "06:30"
                        },
                        "cron": {
                            "dayOfWeek": "Friday",
                            "time": "06:30"
                        }
                    },
                    "finish": {
                        "time": "23:50",
                        "utc": {
                            "dayOfWeek": "Friday",
                            "time": "18:20"
                        },
                        "cron": {
                            "dayOfWeek": "Friday",
                            "time": "18:20"
                        }
                    },
                    "open": true
                },
                {
                    "day": "Saturday",
                    "start": {
                        "time": "00:00",
                        "utc": {
                            "dayOfWeek": "Friday",
                            "time": "18:30"
                        },
                        "cron": {
                            "dayOfWeek": "Friday",
                            "time": "18:30"
                        }
                    },
                    "finish": {
                        "time": "00:00",
                        "utc": {
                            "dayOfWeek": "Friday",
                            "time": "18:30"
                        },
                        "cron": {
                            "dayOfWeek": "Friday",
                            "time": "18:30"
                        }
                    },
                    "open": false
                },
                {
                    "day": "Sunday",
                    "start": {
                        "time": "00:00",
                        "utc": {
                            "dayOfWeek": "Saturday",
                            "time": "18:30"
                        },
                        "cron": {
                            "dayOfWeek": "Saturday",
                            "time": "18:30"
                        }
                    },
                    "finish": {
                        "time": "00:00",
                        "utc": {
                            "dayOfWeek": "Saturday",
                            "time": "18:30"
                        },
                        "cron": {
                            "dayOfWeek": "Saturday",
                            "time": "18:30"
                        }
                    },
                    "open": false
                }
            ],
            "active": true,
            "type": "custom",
            "timezone": {
                "name": "Asia/Kolkata",
                "utc": "+05:30"
            },
            "_updatedAt": "2022-11-28T10:41:17.303Z"
        }
    ],
    "count": 2,
    "offset": 0,
    "total": 2,
    "success": true
}as
```
{% endtab %}

{% tab title="Response with name parameter" %}
```json
{
    "businessHours": [
        {
            "_id": "62b1f74aa98c5b539adc912c",
            "ts": "2022-06-21T16:52:26.386Z",
            "name": "indian support time ",
            "workHours": [
                {
                    "day": "Monday",
                    "start": {
                        "time": "10:00",
                        "utc": {
                            "dayOfWeek": "Monday",
                            "time": "04:30"
                        },
                        "cron": {
                            "dayOfWeek": "Monday",
                            "time": "04:30"
                        }
                    },
                    "finish": {
                        "time": "12:00",
                        "utc": {
                            "dayOfWeek": "Monday",
                            "time": "06:30"
                        },
                        "cron": {
                            "dayOfWeek": "Monday",
                            "time": "06:30"
                        }
                    },
                    "open": true
                },
                {
                    "day": "Tuesday",
                    "start": {
                        "time": "00:00",
                        "utc": {
                            "dayOfWeek": "Monday",
                            "time": "18:30"
                        },
                        "cron": {
                            "dayOfWeek": "Monday",
                            "time": "18:30"
                        }
                    },
                    "finish": {
                        "time": "23:00",
                        "utc": {
                            "dayOfWeek": "Tuesday",
                            "time": "17:30"
                        },
                        "cron": {
                            "dayOfWeek": "Tuesday",
                            "time": "17:30"
                        }
                    },
                    "open": true
                },
                {
                    "day": "Wednesday",
                    "start": {
                        "time": "08:00",
                        "utc": {
                            "dayOfWeek": "Wednesday",
                            "time": "02:30"
                        },
                        "cron": {
                            "dayOfWeek": "Wednesday",
                            "time": "02:30"
                        }
                    },
                    "finish": {
                        "time": "23:00",
                        "utc": {
                            "dayOfWeek": "Wednesday",
                            "time": "17:30"
                        },
                        "cron": {
                            "dayOfWeek": "Wednesday",
                            "time": "17:30"
                        }
                    },
                    "open": true
                },
                {
                    "day": "Thursday",
                    "start": {
                        "time": "10:00",
                        "utc": {
                            "dayOfWeek": "Thursday",
                            "time": "04:30"
                        },
                        "cron": {
                            "dayOfWeek": "Thursday",
                            "time": "04:30"
                        }
                    },
                    "finish": {
                        "time": "01:00",
                        "utc": {
                            "dayOfWeek": "Wednesday",
                            "time": "19:30"
                        },
                        "cron": {
                            "dayOfWeek": "Wednesday",
                            "time": "19:30"
                        }
                    },
                    "open": true
                },
                {
                    "day": "Friday",
                    "start": {
                        "time": "12:00",
                        "utc": {
                            "dayOfWeek": "Friday",
                            "time": "06:30"
                        },
                        "cron": {
                            "dayOfWeek": "Friday",
                            "time": "06:30"
                        }
                    },
                    "finish": {
                        "time": "23:50",
                        "utc": {
                            "dayOfWeek": "Friday",
                            "time": "18:20"
                        },
                        "cron": {
                            "dayOfWeek": "Friday",
                            "time": "18:20"
                        }
                    },
                    "open": true
                },
                {
                    "day": "Saturday",
                    "start": {
                        "time": "00:00",
                        "utc": {
                            "dayOfWeek": "Friday",
                            "time": "18:30"
                        },
                        "cron": {
                            "dayOfWeek": "Friday",
                            "time": "18:30"
                        }
                    },
                    "finish": {
                        "time": "00:00",
                        "utc": {
                            "dayOfWeek": "Friday",
                            "time": "18:30"
                        },
                        "cron": {
                            "dayOfWeek": "Friday",
                            "time": "18:30"
                        }
                    },
                    "open": false
                },
                {
                    "day": "Sunday",
                    "start": {
                        "time": "00:00",
                        "utc": {
                            "dayOfWeek": "Saturday",
                            "time": "18:30"
                        },
                        "cron": {
                            "dayOfWeek": "Saturday",
                            "time": "18:30"
                        }
                    },
                    "finish": {
                        "time": "00:00",
                        "utc": {
                            "dayOfWeek": "Saturday",
                            "time": "18:30"
                        },
                        "cron": {
                            "dayOfWeek": "Saturday",
                            "time": "18:30"
                        }
                    },
                    "open": false
                }
            ],
            "active": true,
            "type": "custom",
            "timezone": {
                "name": "Asia/Kolkata",
                "utc": "+05:30"
            },
            "_updatedAt": "2022-11-28T10:41:17.303Z"
        }
    ],
    "count": 1,
    "offset": 0,
    "total": 1,
    "success": true
}
```
{% endtab %}
{% endtabs %}
