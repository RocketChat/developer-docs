# Get Agent Analytics Overview

Get the analytics overview for agents in your workspace.

{% hint style="info" %}
* It requires the `view-livechat-manager` [permission](https://docs.rocket.chat/use-rocket.chat/workspace-administration/permissions).
{% endhint %}

| URL                                         | Requires Auth | HTTP Method |
| ------------------------------------------- | ------------- | ----------- |
| `/api/v1/livechat/analytics/agent-overview` | `YES`         | `GET`       |

## Headers

<table><thead><tr><th width="179">Argument</th><th width="169">Example</th><th width="143">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>X-User-Id</code></td><td><code>myuser-name</code></td><td>Required</td><td>The authenticated user ID.</td></tr><tr><td><code>X-Auth-Token</code></td><td><code>myauth-token</code></td><td>Required</td><td>Auth token.</td></tr></tbody></table>

## Query Parameter

<table><thead><tr><th width="144">Argument</th><th width="318">Example</th><th>Required</th><th>Description</th></tr></thead><tbody><tr><td><code>name</code></td><td><code>Total_conversations</code></td><td>Required</td><td>The name of the data you want to get.</td></tr><tr><td><code>from</code></td><td>2019-05-22T12:11:45.392Z</td><td>Required</td><td>The start date</td></tr><tr><td><code>to</code></td><td>2023-05-22T12:11:45.392Z</td><td>Required</td><td>The end date</td></tr><tr><td><code>departmentId</code></td><td><code>jsi9w0oakusssjsk</code></td><td>Optional</td><td>The department Id to return results for.</td></tr></tbody></table>

**The available options for the `name` parameter includes the following:**

* Total\_conversations&#x20;
* Avg\_chat\_duration&#x20;
* Total\_messages&#x20;
* Avg\_first\_response\_time&#x20;
* Best\_first\_response\_time&#x20;
* Avg\_response\_time&#x20;
* Avg\_reaction\_time

## Example Call

```bash
curl -L -X GET 'http://localhost:3000/api/v1/livechat/analytics/agent-overview?name=Total_conversations&from=2019-05-22T12%3A11%3A45.392Z&to=2023-05-22T12%3A11%3A45.392Z' \
-H 'x-auth-token: 6gwMfYPDoQzMCAnwjP5iILveZINplU7V-1DYzkhhxsc' \
-H 'x-user-id: rmbMnnpqkuxEbrajt'
```

## Example Result&#x20;

```javascript
{
    "head": [
        {
            "name": "Agent"
        },
        {
            "name": "%_of_conversations"
        }
    ],
    "data": [
        {
            "name": "harmeet.kour",
            "value": "44.63%"
        },
        {
            "name": "renato.becker",
            "value": "8.20%"
        },
        {
            "name": "bot",
            "value": "7.24%"
        },
        {
            "name": "murtaza98",
            "value": "4.58%"
        },
        {
            "name": "Demo",
            "value": "4.22%"
        },
        {
            "name": "janaina.coelho",
            "value": "3.26%"
        },
        {
            "name": "sam1",
            "value": "3.14%"
        },
        {
            "name": "rocket.cat",
            "value": "2.65%"
        },
        {
            "name": "test",
            "value": "2.53%"
        },
        {
            "name": "guilherme.gazzo",
            "value": "2.29%"
        },
        {
            "name": "chitti",
            "value": "2.29%"
        },
        {
            "name": "anu",
            "value": "2.05%"
        },
        {
            "name": "murtaza.admin",
            "value": "1.93%"
        },
        {
            "name": "arthurdebiase",
            "value": "1.09%"
        },
        {
            "name": "tiago.evangelista",
            "value": "0.97%"
        },
        {
            "name": "joseph.pearce",
            "value": "0.97%"
        },
        {
            "name": "harry",
            "value": "0.84%"
        },
        {
            "name": "Test.bot",
            "value": "0.60%"
        },
        {
            "name": "arthur.debiase",
            "value": "0.48%"
        },
        {
            "name": "user.five",
            "value": "0.48%"
        },
        {
            "name": "common-AB",
            "value": "0.48%"
        },
        {
            "name": "levyazevedo",
            "value": "0.36%"
        },
        {
            "name": "B1",
            "value": "0.36%"
        },
   
        {
            "name": "kevin.aleman",
            "value": "0.12%"
        },
        {
            "name": "Faria",
            "value": "0.12%"
        },
        {
            "name": "caue.felchar",
            "value": "0.12%"
        },
        {
            "name": "testejjj",
            "value": "0.12%"
        },
        {
            "name": "hugo.costa",
            "value": "0.12%"
        },
        {
            "name": "amit",
            "value": "0.12%"
        },
        {
            "name": "gogo",
            "value": "0.12%"
        }
    ],
    "success": true
}
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
