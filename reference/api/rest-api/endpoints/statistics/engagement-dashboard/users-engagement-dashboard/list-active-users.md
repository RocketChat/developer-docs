# List Active Users

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Retrieve the metrics of active users in the workspace during a specific period.

{% hint style="info" %}
It requires `view-engagement-dashboard` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
{% endhint %}

| URL                                               | Requires Auth | HTTP Method |
| ------------------------------------------------- | ------------- | ----------- |
| `/api/v1/engagement-dashboard/users/active-users` | `yes`         | `GET`       |

## &#x20;Query Parameter

| Argument | Example                    | Required | Description     |
| -------- | -------------------------- | -------- | --------------- |
| `start`  | `2011-10-05T14:48:00.000Z` | Required | The start date. |
| `end`    | `2023-10-05T14:48:00.000Z` | Required | The end date.   |

## Example Call

```bash
curl --location 'http://localhost:3000/api/v1/engagement-dashboard/users/new-users?start=2011-10-05T14%3A48%3A00.000Z&end=2023-10-05T14%3A48%3A00.000Z' \
--header 'x-auth-token: GENgWDE3-KV1BvVbnIOvpTq5RhJOQQr4XKCAsVLtFYu' \
--header 'x-user-id: 2tTEqR7ZNMJ4HGGNa'
```

## Example Result

### Success

```json
{
    "month": [
        {
            "usersList": [
                "rYhzFRd2QZjNwAAXX"
            ],
            "users": 1,
            "day": 5,
            "month": 5,
            "year": 2023
        },
        {
            "usersList": [
                "rYhzFRd2QZjNwAAXX"
            ],
            "users": 1,
            "day": 4,
            "month": 5,
            "year": 2023
        },
        {
            "usersList": [
                "rYhzFRd2QZjNwAAXX"
            ],
            "users": 1,
            "day": 3,
            "month": 5,
            "year": 2023
        },
        {
            "usersList": [
                "rYhzFRd2QZjNwAAXX"
            ],
            "users": 1,
            "day": 2,
            "month": 5,
            "year": 2023
        },
        {
            "usersList": [
                "rbAXPnMktTFbNpwtJ"
            ],
            "users": 1,
            "day": 1,
            "month": 5,
            "year": 2023
        },
        {
            "usersList": [
                "rYhzFRd2QZjNwAAXX"
            ],
            "users": 1,
            "day": 29,
            "month": 4,
            "year": 2023
        },
        {
            "usersList": [
                "rYhzFRd2QZjNwAAXX"
            ],
            "users": 1,
            "day": 28,
            "month": 4,
            "year": 2023
        },
        {
            "usersList": [
                "rYhzFRd2QZjNwAAXX",
                "hFDuCPam7sWziWFYa"
            ],
            "users": 2,
            "day": 27,
            "month": 4,
            "year": 2023
        },
        {
            "usersList": [
                "rbAXPnMktTFbNpwtJ"
            ],
            "users": 1,
            "day": 26,
            "month": 4,
            "year": 2023
        },
        {
            "usersList": [
                "rbAXPnMktTFbNpwtJ"
            ],
            "users": 1,
            "day": 24,
            "month": 4,
            "year": 2023
        },
        {
            "usersList": [
                "rbAXPnMktTFbNpwtJ",
                "rYhzFRd2QZjNwAAXX"
            ],
            "users": 2,
            "day": 21,
            "month": 4,
            "year": 2023
        },
        {
            "usersList": [
                "rYhzFRd2QZjNwAAXX"
            ],
            "users": 1,
            "day": 19,
            "month": 4,
            "year": 2023
        },
        {
            "usersList": [
                "rbAXPnMktTFbNpwtJ",
                "rYhzFRd2QZjNwAAXX"
            ],
            "users": 2,
            "day": 18,
            "month": 4,
            "year": 2023
        },
        {
            "usersList": [
                "rbAXPnMktTFbNpwtJ",
                "9iN96PXnDK7XAYESA"
            ],
            "users": 2,
            "day": 17,
            "month": 4,
            "year": 2023
        }
    ],
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **No Permission**: This occurs when the authenticated user doesn't have the   `view-engagement-dashboard` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
* **Invalid Date**: This occurs when the `start` or `end` date does not follow the accepted format ( `2023-10-05T14:48:00.000Z`).

{% tabs %}
{% tab title="Authorization" %}
```json
{
    "status": "error",
    "message": "You must be logged in to do this."
}
```
{% endtab %}

{% tab title="No Permission" %}
```json
{
    "success": false,
    "error": "User does not have the permissions required for this action [error-unauthorized]"
}
```
{% endtab %}

{% tab title="Invalid Date" %}
```json
{
    "success": false,
    "error": "Match error: Failed Match.Where validation in field start"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 3.1.0   | Added       |
