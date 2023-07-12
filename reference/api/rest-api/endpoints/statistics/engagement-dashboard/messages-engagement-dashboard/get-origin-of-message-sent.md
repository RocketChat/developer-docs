# Get Origin of Message Sent

Get the origin of messages sent during a specific period. It highlights the number of messages sent in private channels, private chats, and public channels.

{% hint style="info" %}
It requires `view-engagement-dashboard` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
{% endhint %}

| URL                                            | Requires Auth | HTTP Method |
| ---------------------------------------------- | ------------- | ----------- |
| `/api/v1/engagement-dashboard/messages/origin` | `yes`         | `GET`       |

## &#x20;Query Parameter

| Argument | Example                    | Required | Description     |
| -------- | -------------------------- | -------- | --------------- |
| `start`  | `2023-05-20T00:00:00.000Z` | Required | The start date. |
| `end`    | `2023-10-05T14:48:00.000Z` | Required | The end date.   |

## Example Call

```bash
curl --location 'http://localhost:3000/api/v1/engagement-dashboard/messages/origin?start=2023-02-20T00%3A00%3A00.000Z&end=2023-05-30T00%3A00%3A00.000Z' \
--header 'x-auth-token: HF0U3GBQHzC0pL_f_XXFHEfgXR8041XGldg2m_z8JQ0' \
--header 'x-user-id: rbAXPnMktTFbNpwtJ'
```

## Example Result

### Success

```json
{
    "origins": [
        {
            "messages": 7302,
            "t": "c"
        },
        {
            "messages": 1147,
            "t": "d"
        },
        {
            "messages": 122,
            "t": "p"
        }
    ],
    "success": true
}
```

{% hint style="info" %}
`t`denotes the type of [room](https://docs.rocket.chat/use-rocket.chat/user-guides/rooms) where the messages are sent.

* `d` represents `Private Chats`
* `c` represents `Public Channels`
* `p` represents `Private Channels`
{% endhint %}

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
