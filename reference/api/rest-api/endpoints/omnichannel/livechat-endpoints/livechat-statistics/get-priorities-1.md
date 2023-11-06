# Get Analytics Overview

Get the overview of omnichannel analytics in your workspace.

{% hint style="info" %}
* It requires the `view-livechat-manager` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
{% endhint %}

<table><thead><tr><th width="163">HTTP Method</th><th width="332">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/analytics/overview</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

## Query Parameters

<table><thead><tr><th width="178">Key</th><th width="275">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>name</code><mark style="color:red;"><code>*</code></mark></td><td><code>Conversations</code></td><td><p>The data that you want to get. The available options are: </p><ul><li>Conversations</li><li>Productivity</li></ul></td></tr><tr><td><code>from</code><mark style="color:red;"><code>*</code></mark></td><td><code>2019-05-22T12:11:45.392Z</code></td><td>The start date</td></tr><tr><td><code>to</code><mark style="color:red;"><code>*</code></mark></td><td><code>2023-05-22T12:11:45.392Z</code></td><td>The end date</td></tr><tr><td><code>departmentId</code></td><td><code>jsi9w0oakusss</code></td><td>The department ID to return results for.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl -L -X GET 'http://localhost:3000/api/v1/livechat/analytics/overview?name=Conversations&from=2019-05-22T12%3A11%3A45.392Z&to=2023-05-22T12%3A11%3A45.392Z' \
-H 'x-auth-token: qlHA60g5JQjJJG7C_8MgXoFnOiRQ8X9TWVVq4AcQeFb' \
-H 'x-user-id: rbAXPnMktTFbNpwtJ'
```
{% endcode %}

## Example Response

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
