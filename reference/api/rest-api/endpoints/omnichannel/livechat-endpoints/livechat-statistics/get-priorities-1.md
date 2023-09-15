# Get Analytics Overview

Get the overview of omnichannel analytics in your workspace.

{% hint style="info" %}
* It requires the `view-livechat-manager` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
{% endhint %}

| URL                                   | Requires Auth | HTTP Method |
| ------------------------------------- | ------------- | ----------- |
| `/api/v1/livechat/analytics/overview` | `YES`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                |
| -------------- | -------------- | -------- | -------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | The authenticated user ID. |
| `X-Auth-Token` | `myauth-token` | Required | Auth token.                |

## Query Parameter

<table><thead><tr><th width="144">Argument</th><th width="318">Example</th><th>Required</th><th>Description</th></tr></thead><tbody><tr><td><code>name</code></td><td><code>Conversations</code></td><td>Required</td><td>The name of the data you want to get</td></tr><tr><td><code>from</code></td><td><code>2019-05-22T12:11:45.392Z</code></td><td>Required</td><td>The start date</td></tr><tr><td><code>to</code></td><td><code>2023-05-22T12:11:45.392Z</code></td><td>Required</td><td>The end date</td></tr><tr><td><code>departmentId</code></td><td><code>jsi9w0oakusss</code></td><td>Optional</td><td>The department Id to return results for.</td></tr></tbody></table>

**The available options for the `name` parameter includes the following:**

* Conversations&#x20;
* Productivity

## Example Call

```bash
curl -L -X GET 'http://localhost:3000/api/v1/livechat/analytics/overview?name=Conversations&from=2019-05-22T12%3A11%3A45.392Z&to=2023-05-22T12%3A11%3A45.392Z' \
-H 'x-auth-token: qlHA60g5JQjJJG7C_8MgXoFnOiRQ8X9TWVVq4AcQeFb' \
-H 'x-user-id: rbAXPnMktTFbNpwtJ'
```

## Example Result

### Success

```javascript
[
    {
        "title": "Total_conversations",
        "value": 1086
    },
    {
        "title": "Open_conversations",
        "value": 119
    },
    {
        "title": "On_Hold_conversations",
        "value": 1
    },
    {
        "title": "Total_messages",
        "value": 4892
    },
    {
        "title": "Busiest_day",
        "value": "Tuesday"
    },
    {
        "title": "Conversations_per_day",
        "value": "0.74"
    },
    {
        "title": "Busiest_time",
        "value": "7AM- 8AM"
    }
]
```

### Error

Any of the following errors can occur on the endpoint.

* **Authorization**: Requires an authentication token for the request to be made.
* **No Permission**: This occurs when the authenticated user doesn't have the  `view-livechat-manager` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).

{% tabs %}
{% tab title=" Authorization" %}
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
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 6.4.0   | Added       |
