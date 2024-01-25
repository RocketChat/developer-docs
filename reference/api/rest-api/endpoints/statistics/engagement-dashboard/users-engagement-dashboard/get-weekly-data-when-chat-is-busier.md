# Get Weekly Data When Chat is Busier

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Retrieves weekly data when chat is busier.&#x20;

{% hint style="info" %}
It requires `view-engagement-dashboard` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
{% endhint %}

| URL                                                          | Requires Auth | HTTP Method |
| ------------------------------------------------------------ | ------------- | ----------- |
| `/api/v1/engagement-dashboard/users/chat-busier/weekly-data` | `yes`         | `GET`       |

## &#x20;Query Parameter

| Argument | Example                    | Required | Description                                                                       |
| -------- | -------------------------- | -------- | --------------------------------------------------------------------------------- |
| `start`  | `2023-05-19T00:00:00.000Z` | Required | The start date. It retrieves data for one week prior to the specified start date. |

## Example Call

```bash
curl --location 'http://localhost:3000/api/v1/engagement-dashboard/users/chat-busier/weekly-data?start=2023-05-19T00%3A00%3A00.000Z' \
--header 'x-auth-token: HF0U3GBQHzC0pL_f_XXFHEfgXR8041XGldg2m_z8JQ0' \
--header 'x-user-id: rbAXPnMktTFbNpwtJ'

```

## Example Result

### Success

```json
{
    "month": [
        {
            "users": 1,
            "day": 19,
            "month": 5,
            "year": 2023
        },
        {
            "users": 3,
            "day": 16,
            "month": 5,
            "year": 2023
        },
        {
            "users": 3,
            "day": 15,
            "month": 5,
            "year": 2023
        },
        {
            "users": 2,
            "day": 14,
            "month": 5,
            "year": 2023
        },
        {
            "users": 2,
            "day": 13,
            "month": 5,
            "year": 2023
        },
        {
            "users": 4,
            "day": 12,
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
