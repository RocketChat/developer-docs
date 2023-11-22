# Get Departments by ID

Get a list of departments by department IDs.

<table><thead><tr><th width="163">HTTP Method</th><th width="305">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/department.listByIds</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permissions required:

* `view-livechat-departments`
* `view-l-room`
{% endhint %}

## Query Parameters

<table><thead><tr><th width="209.33333333333331">Key</th><th width="243">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>ids</code><mark style="color:red;"><code>*</code></mark></td><td><code>4LCeYmCHHnQ3EDBgf</code></td><td>The department ID.</td></tr><tr><td><code>ids</code><mark style="color:red;"><code>*</code></mark></td><td><code>CAJioQNAvLnYWTy8i</code></td><td>The department ID.</td></tr><tr><td><code>ids</code></td><td><code>mHcx4rbi7htAmCCR5</code></td><td>The department ID.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request GET 'http://localhost:3000/api/v1/livechat/department.listByIds?
    ids=4LCeYmCHHnQ3EDBgf
    &ids=CAJioQNAvLnYWTy8i
    &ids=mHcx4rbi7htAmCCR5\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```
{% endcode %}

## Example Response

```json
{
    "departments": [
        {
            "_id": "4LCeYmCHHnQ3EDBgf",
            "enabled": true,
            "name": "Chatbot Sales",
            "description": "",
            "showOnRegistration": false,
            "showOnOfflineForm": false,
            "requestTagBeforeClosingChat": false,
            "email": "chatbotSales@g.c",
            "chatClosingTags": [],
            "offlineMessageChannelName": "",
            "abandonedRoomsCloseCustomMessage": "",
            "waitingQueueMessage": "",
            "departmentsAllowedToForward": "",
            "_updatedAt": "2021-07-15T15:11:16.856Z",
            "numAgents": 4,
            "ancestors": []
        },
        {
            "_id": "CAJioQNAvLnYWTy8i",
            "enabled": true,
            "name": "Support",
            "description": "",
            "showOnRegistration": true,
            "showOnOfflineForm": true,
            "requestTagBeforeClosingChat": false,
            "email": "mary@rocket.chat",
            "maxNumberSimultaneousChat": "",
            "waitingQueueMessage": "",
            "type": "d",
            "numAgents": 28,
            "_updatedAt": "2021-07-21T23:54:35.574Z",
            "ancestors": [
                "sriw2wmP2Zz2pPrre"
            ],
            "chatClosingTags": [],
            "abandonedRoomsCloseCustomMessage": "",
            "departmentsAllowedToForward": "",
            "offlineMessageChannelName": "",
            "visitorInactivityTimeoutInSeconds": "10",
            "parentId": "sriw2wmP2Zz2pPrre"
        },
        {
            "_id": "mHcx4rbi7htAmCCR5",
            "enabled": true,
            "name": "Chatbot Support",
            "description": "",
            "showOnRegistration": false,
            "showOnOfflineForm": false,
            "requestTagBeforeClosingChat": false,
            "email": "chatbotSupport@g.c",
            "chatClosingTags": [],
            "offlineMessageChannelName": "",
            "abandonedRoomsCloseCustomMessage": "",
            "waitingQueueMessage": "",
            "departmentsAllowedToForward": "",
            "_updatedAt": "2021-06-28T22:10:01.371Z",
            "numAgents": 3,
            "ancestors": [
                "sriw2wmP2Zz2pPrre"
            ],
            "parentId": "sriw2wmP2Zz2pPrre"
        }
    ],
    "success": true
}
```
