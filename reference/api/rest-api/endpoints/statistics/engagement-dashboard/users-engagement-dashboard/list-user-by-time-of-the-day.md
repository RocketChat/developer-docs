# List User By Time of the Day

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Retrieve users by hours at a particular time of the day in a week.

{% hint style="info" %}
It requires `view-engagement-dashboard` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
{% endhint %}

| URL                                                                     | Requires Auth | HTTP Method |
| ----------------------------------------------------------------------- | ------------- | ----------- |
| `/api/v1/engagement-dashboard/users/users-by-time-of-the-day-in-a-week` | `yes`         | `GET`       |

## &#x20;Query Parameter

| Argument | Example                    | Required | Description     |
| -------- | -------------------------- | -------- | --------------- |
| `start`  | `2023-04-29T14:48:00.000Z` | Required | The start date. |
| `end`    | `2023-05-02T14:48:00.000Z` | Required | The end date.   |

## Example Call

```bash
curl --location 'http://localhost:3000/api/v1/engagement-dashboard/users/users-by-time-of-the-day-in-a-week?start=2023-04-29T14%3A48%3A00.000Z&end=2023-05-02T14%3A48%3A00.000Z' \
--header 'x-auth-token: HF0U3GBQHzC0pL_f_XXFHEfgXR8041XGldg2m_z8JQ0' \
--header 'x-user-id: rbAXPnMktTFbNpwtJ'
```

## Example Result

### Success

```json
{
    "week": [
        {
            "users": 1,
            "hour": 23,
            "day": 2,
            "month": 5,
            "year": 2023
        },
        {
            "users": 1,
            "hour": 22,
            "day": 2,
            "month": 5,
            "year": 2023
        },
        {
            "users": 1,
            "hour": 21,
            "day": 2,
            "month": 5,
            "year": 2023
        },
        {
            "users": 1,
            "hour": 20,
            "day": 2,
            "month": 5,
            "year": 2023
        },
        {
            "users": 1,
            "hour": 19,
            "day": 2,
            "month": 5,
            "year": 2023
        },
        {
            "users": 1,
            "hour": 18,
            "day": 2,
            "month": 5,
            "year": 2023
        },
        {
            "users": 1,
            "hour": 17,
            "day": 2,
            "month": 5,
            "year": 2023
        },
        {
            "users": 1,
            "hour": 16,
            "day": 2,
            "month": 5,
            "year": 2023
        },
        {
            "users": 1,
            "hour": 15,
            "day": 2,
            "month": 5,
            "year": 2023
        },
        {
            "users": 1,
            "hour": 14,
            "day": 2,
            "month": 5,
            "year": 2023
        },
        {
            "users": 1,
            "hour": 1,
            "day": 1,
            "month": 5,
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
