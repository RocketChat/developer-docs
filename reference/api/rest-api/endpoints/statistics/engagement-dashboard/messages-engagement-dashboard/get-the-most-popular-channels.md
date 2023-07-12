# Get the Most Popular Channels

Retrieves the top 5 popular channels in your workspace by the number of messages sent.

{% hint style="info" %}
It requires `view-engagement-dashboard` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
{% endhint %}

| URL                                                              | Requires Auth | HTTP Method |
| ---------------------------------------------------------------- | ------------- | ----------- |
| `api/v1/engagement-dashboard/messages/top-five-popular-channels` | `yes`         | `GET`       |

## &#x20;Query Parameter

<table><thead><tr><th width="144">Argument</th><th width="318">Example</th><th>Required</th><th>Description</th></tr></thead><tbody><tr><td><code>start</code></td><td><code>2023-05-20T00:00:00.000Z</code></td><td>Required</td><td>The start date.</td></tr><tr><td><code>end</code></td><td><code>2023-10-05T14:48:00.000Z</code></td><td>Required</td><td>The end date.</td></tr></tbody></table>

## Example Call

```bash
curl --location 'http://localhost:3000/api/v1/engagement-dashboard/messages/top-five-popular-channels?start=2023-05-20T00%3A00%3A00.000Z&end=2023-05-30T00%3A00%3A00.000Z' \
--header 'x-auth-token: HF0U3GBQHzC0pL_f_XXFHEfgXR8041XGldg2m_z8JQ0' \
--header 'x-user-id: rbAXPnMktTFbNpwtJ'
```

## Example Result

### Success

```json
{
    "channels": [
        {
            "messages": 727,
            "t": "d",
            "usernames": [
                "google-calendar.bot",
                "pavithra.sudhakar"
            ]
        },
        {
            "messages": 26,
            "t": "d",
            "usernames": [
                "funke.olasupo",
                "google-calendar.bot"
            ]
        },
        {
            "messages": 2,
            "t": "d",
            "usernames": [
                "funke.olasupo",
                "rocket.cat"
            ]
        },
        {
            "messages": 1,
            "t": "d",
            "usernames": [
                "faria.masood",
                "rocket.cat"
            ]
        },
        {
            "messages": 1,
            "t": "d",
            "usernames": [
                "janaina.coelho",
                "rocket.cat"
            ]
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
