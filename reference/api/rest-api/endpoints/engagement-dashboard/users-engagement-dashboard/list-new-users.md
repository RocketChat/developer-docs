# List New Users

Retrieve the metrics of newly registered users during a specific period.

{% hint style="info" %}
It requires `view-engagement-dashboard` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
{% endhint %}

| URL                                            | Requires Auth | HTTP Method |
| ---------------------------------------------- | ------------- | ----------- |
| `/api/v1/engagement-dashboard/users/new-users` | `yes`         | `GET`       |

## &#x20;Query Parameter

| Argument | Example                    | Required | Description     |
| -------- | -------------------------- | -------- | --------------- |
| `start`  | `2011-10-05T14:48:00.000Z` | Required | The start date. |
| `end`    | `2023-10-05T14:48:00.000Z` | Required | The end date.   |

## Example Call

```bash
curl --location 'http://localhost:3000/api/v1/engagement-dashboard/users/new-users?start=2011-10-05T14%3A48%3A00.000Z&end=2023-10-05T14%3A48%3A00.000Z' \
--header 'x-auth-token: HF0U3GBQHzC0pL_f_XXFHEfgXR8041XGldg2m_z8JQ0' \
--header 'x-user-id: rbAXPnMktTFbNpwtJ'
```

## Example Result

### Success

```json
{
    "days": [
        {
            "day": "2023-05-23T00:00:00.000Z",
            "users": 2
        },
        {
            "day": "2023-05-16T00:00:00.000Z",
            "users": 1
        },
        {
            "day": "2023-05-12T00:00:00.000Z",
            "users": 1
        },
        {
            "day": "2023-05-11T00:00:00.000Z",
            "users": 1
        },
        {
            "day": "2023-03-31T00:00:00.000Z",
            "users": 1
        },
        {
            "day": "2023-03-28T00:00:00.000Z",
            "users": 2
        },
        {
            "day": "2023-03-13T00:00:00.000Z",
            "users": 1
        },
        {
            "day": "2023-03-07T00:00:00.000Z",
            "users": 2
        },
        {
            "day": "2023-03-02T00:00:00.000Z",
            "users": 2
        },
        {
            "day": "2023-02-20T00:00:00.000Z",
            "users": 4
        },
        {
            "day": "2023-02-09T00:00:00.000Z",
            "users": 1
        },
        {
            "day": "2023-02-06T00:00:00.000Z",
            "users": 6
        },
        {
            "day": "2023-02-01T00:00:00.000Z",
            "users": 1
        },
        {
            "day": "2023-01-24T00:00:00.000Z",
            "users": 1
        },
        {
            "day": "2023-01-17T00:00:00.000Z",
            "users": 1
        }
    ],
    "period": {
        "count": 27,
        "variation": 27
    },
    "yesterday": {
        "count": 0,
        "variation": 0
    },
    "success": true
}
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **No Permission**: Occurs when the authenticated user doesn't have the   `view-engagement-dashboard` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
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
