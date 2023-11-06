# Get Agent Analytics Overview

Get the analytics overview for the agents in your workspace.

{% hint style="info" %}
You need the `view-livechat-manager` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
{% endhint %}

<table><thead><tr><th width="163">HTTP Method</th><th width="332">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/analytics/agent-overview</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

## Query Parameters

<table><thead><tr><th width="174">Key</th><th width="285">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>name</code><mark style="color:red;"><code>*</code></mark></td><td><code>Total_conversations</code></td><td><p>The data that you want to get. The available options are:</p><ul><li>Total_conversations</li><li>Avg_chat_duration</li><li>Total_messages</li><li>Avg_first_response_time</li><li>Best_first_response_time</li><li>Avg_response_time</li><li>Avg_reaction_time</li></ul></td></tr><tr><td><code>from</code><mark style="color:red;"><code>*</code></mark></td><td>2019-05-22T12:11:45.392Z</td><td>The start date</td></tr><tr><td><code>to</code><mark style="color:red;"><code>*</code></mark></td><td>2023-05-22T12:11:45.392Z</td><td>The end date</td></tr><tr><td><code>departmentId</code></td><td><code>jsi9w0oakusssjsk</code></td><td>The department ID to return results for.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl -L -X GET 'http://localhost:3000/api/v1/livechat/analytics/agent-overview?name=Total_messages&from=2019-05-22T12%3A11%3A45.392Z&to=2023-05-22T12%3A11%3A45.392Z' \
-H 'x-auth-token: 6gwMfYPDoQzMCAnwjP5iILveZINplU7V-1DYzkhhxsc' \
-H 'x-user-id: rmbMnnpqkuxEbrajt'
```
{% endcode %}

## Example Response&#x20;

```json
{
    "head": [
        {
            "name": "Agent"
        },
        {
            "name": "Total_messages"
        }
    ],
    "data": [
        {
            "name": "kim",
            "value": "25"
        },
        {
            "name": "jane",
            "value": "50"
        },
        {
            "name": "baek",
            "value": "44"
        },
        {
            "name": "sam",
            "value": "111"
        },
        {
            "name": "john",
            "value": "67"
        },
        {
            "name": "aline",
            "value": "90"
        },
        {
            "name": "addie",
            "value": "49"
        }
    ],
    "success": true
}
```

### Errors

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
