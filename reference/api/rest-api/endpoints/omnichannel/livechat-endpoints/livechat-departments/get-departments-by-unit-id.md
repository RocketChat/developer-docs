# Get Departments by Unit ID

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Gives departments included in a specific unit ID.

{% hint style="warning" %}
![](../../../../../../../.gitbook/assets/Deprecated.png) This endpoint has been renamed to [get-department-by-unit-id.md](../livechat-units/get-department-by-unit-id.md "mention") as from Rocket.Chat `5.0`
{% endhint %}

<table><thead><tr><th width="163">HTTP Method</th><th width="305">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>api/v1/livechat/departments.by-unit/:unitId</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Path Variables

<table><thead><tr><th width="199.33333333333331">Key</th><th>Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>unitId</code><mark style="color:red;"><code>*</code></mark></td><td><code>sriw2wmP2Zz2pPrre</code></td><td>The unit ID.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request GET 'http://localhost:3000///api/v1/livechat/departments.by-unit/:unitId \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```
{% endcode %}

## Example Response

```json
{
    "departments": [
        {
            "_id": "Yi87Ju7eTHiZQ7CJt",
            "enabled": false,
            "name": "Customer Success",
            "description": "TEST",
            "showOnRegistration": false,
            "showOnOfflineForm": true,
            "requestTagBeforeClosingChat": false,
            "email": "roger.sab@test.comt",
            "maxNumberSimultaneousChat": "",
            "waitingQueueMessage": "TEST",
            "type": "d",
            "numAgents": 13,
            "_updatedAt": "2021-06-28T22:10:01.360Z",
            "ancestors": [
                "sriw2wmP2Zz2pPrre"
            ],
            "chatClosingTags": [],
            "abandonedRoomsCloseCustomMessage": "",
            "departmentsAllowedToForward": "",
            "offlineMessageChannelName": "",
            "visitorInactivityTimeoutInSeconds": "",
            "parentId": "sriw2wmP2Zz2pPrre"
        },
        {
            "_id": "CAJioQNAvLnYWTy8i",
            "enabled": true,
            "name": "Support",
            "description": "",
            "showOnRegistration": true,
            "showOnOfflineForm": true,
            "requestTagBeforeClosingChat": false,
            "email": "maryna.vdov@test.com",
            "maxNumberSimultaneousChat": "",
            "waitingQueueMessage": "",
            "type": "d",
            "numAgents": 24,
            "_updatedAt": "2021-06-28T22:10:01.373Z",
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
            "_id": "Z2KWYBJQFR7AzfmQL",
            "enabled": false,
            "name": "Support Email",
            "description": "testing emails",
            "showOnRegistration": false,
            "showOnOfflineForm": false,
            "requestTagBeforeClosingChat": false,
            "email": "karina.aes@hotmail.com",
            "chatClosingTags": [],
            "offlineMessageChannelName": "",
            "maxNumberSimultaneousChat": "",
            "visitorInactivityTimeoutInSeconds": "30",
            "abandonedRoomsCloseCustomMessage": "",
            "waitingQueueMessage": "",
            "departmentsAllowedToForward": [
                "qajzu7WaBRoQBpq6Z",
                "4LCeYmCHHnQ3EDBgf"
            ],
            "type": "d",
            "numAgents": 5,
            "_updatedAt": "2021-06-28T22:10:01.347Z",
            "ancestors": [
                "sriw2wmP2Zz2pPrre"
            ],
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
    "count": 4,
    "offset": 0,
    "total": 4,
    "success": true
}
```
