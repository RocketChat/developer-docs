---
description: Gives departments that have not been associated to another unit yet
---

# Departments available by unit Id

![](../../../../../../../.gitbook/assets/enterprise.jpg)

{% hint style="info" %}
![](../../../../../../../.gitbook/assets/Deprecated.png) This endpoint has been renamed to [get-available-departments-by-unit-id.md](../units/get-available-departments-by-unit-id.md "mention") as from Rocket.Chat `5.0`
{% endhint %}

| URL                                                     | Requires Auth | HTTP Method |
| ------------------------------------------------------- | ------------- | ----------- |
| `api/v1/livechat/departments.available-by-unit/:unitId` | `YES`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Path Variables

| Argument | Example             | Required | Description |
| -------- | ------------------- | -------- | ----------- |
| `unitId` | `sriw2wmP2Zz2pPrre` | Required | Unit Id     |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000///api/v1/livechat/departments.available-by-unit/:unitId \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript
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
            "email": "",
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
            "_id": "fqjhjfuygXBRsPBJf",
            "enabled": true,
            "name": "Marketing Support",
            "description": "Issues about merchandising actions",
            "numAgents": 3,
            "showOnRegistration": false,
            "showOnOfflineForm": false,
            "email": "",
            "_updatedAt": "2021-06-15T21:12:35.469Z",
            "maxNumberSimultaneousChat": "",
            "requestTagBeforeClosingChat": false,
            "type": "d",
            "waitingQueueMessage": "",
            "chatClosingTags": [],
            "abandonedRoomsCloseCustomMessage": "",
            "departmentsAllowedToForward": "",
            "offlineMessageChannelName": "",
            "visitorInactivityTimeoutInSeconds": ""
        },
        {
            "_id": "qajzu7WaBRoQBpq6Z",
            "enabled": true,
            "name": "Brazil",
            "description": "",
            "numAgents": 3,
            "showOnRegistration": false,
            "showOnOfflineForm": true,
            "email": "",
            "_updatedAt": "2021-06-23T06:02:02.931Z",
            "chatClosingTags": [],
            "maxNumberSimultaneousChat": "",
            "requestTagBeforeClosingChat": false,
            "type": "d",
            "waitingQueueMessage": "",
            "abandonedRoomsCloseCustomMessage": "",
            "departmentsAllowedToForward": "",
            "offlineMessageChannelName": "",
            "visitorInactivityTimeoutInSeconds": "",
            "ancestors": []
        },
        {
            "_id": "GgYvrkAF63aeQmsh4",
            "enabled": true,
            "name": "Sales",
            "description": "For sales purposes only, we are happy to help",
            "showOnRegistration": true,
            "showOnOfflineForm": true,
            "requestTagBeforeClosingChat": true,
            "email": "",
            "chatClosingTags": [
                "Junk lead",
                "Valuable lead"
            ],
            "maxNumberSimultaneousChat": "",
            "waitingQueueMessage": "",
            "type": "d",
            "numAgents": 20,
            "_updatedAt": "2021-06-27T05:52:01.775Z",
            "abandonedRoomsCloseCustomMessage": "",
            "departmentsAllowedToForward": [
                "qajzu7WaBRoQBpq6Z",
                "CAJioQNAvLnYWTy8i"
            ],
            "visitorInactivityTimeoutInSeconds": "",
            "offlineMessageChannelName": "",
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
            "email": "",
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
            "email": "",
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
            "_id": "BiqbQav59HD2LzXEY",
            "enabled": true,
            "name": "Experimental - Talk to a chatbot",
            "description": "",
            "showOnRegistration": true,
            "showOnOfflineForm": true,
            "requestTagBeforeClosingChat": false,
            "email": "",
            "chatClosingTags": [],
            "offlineMessageChannelName": "",
            "maxNumberSimultaneousChat": "",
            "visitorInactivityTimeoutInSeconds": "",
            "abandonedRoomsCloseCustomMessage": "",
            "waitingQueueMessage": "",
            "departmentsAllowedToForward": "",
            "type": "d",
            "numAgents": 1,
            "_updatedAt": "2021-06-23T09:58:03.429Z",
            "ancestors": []
        },
        {
            "_id": "YiWdMkdbFhk3o9daf",
            "enabled": true,
            "name": "Covid-19-operation-agents",
            "description": "",
            "showOnRegistration": false,
            "showOnOfflineForm": false,
            "requestTagBeforeClosingChat": false,
            "email": "",
            "chatClosingTags": [],
            "offlineMessageChannelName": "",
            "maxNumberSimultaneousChat": "",
            "visitorInactivityTimeoutInSeconds": "",
            "abandonedRoomsCloseCustomMessage": "",
            "waitingQueueMessage": "",
            "departmentsAllowedToForward": "",
            "type": "d",
            "numAgents": 2,
            "_updatedAt": "2021-06-18T18:02:13.263Z",
            "ancestors": []
        },
        {
            "_id": "8MGLTfaKLCbE9CqR8",
            "enabled": false,
            "name": "Demo",
            "description": "",
            "showOnRegistration": false,
            "showOnOfflineForm": false,
            "requestTagBeforeClosingChat": false,
            "email": "demo@rocket.chat",
            "chatClosingTags": [],
            "offlineMessageChannelName": "",
            "maxNumberSimultaneousChat": "",
            "visitorInactivityTimeoutInSeconds": "",
            "abandonedRoomsCloseCustomMessage": "",
            "waitingQueueMessage": "",
            "departmentsAllowedToForward": "",
            "_updatedAt": "2021-06-18T18:02:13.263Z",
            "numAgents": 5,
            "ancestors": []
        },
        {
            "_id": "sLYp3ry7CRizaP3rJ",
            "enabled": false,
            "name": "Sales test",
            "description": "Sales test",
            "showOnRegistration": false,
            "showOnOfflineForm": false,
            "requestTagBeforeClosingChat": false,
            "email": "",
            "chatClosingTags": [],
            "offlineMessageChannelName": "",
            "visitorInactivityTimeoutInSeconds": "60",
            "abandonedRoomsCloseCustomMessage": "",
            "waitingQueueMessage": "welcome!",
            "departmentsAllowedToForward": "",
            "_updatedAt": "2021-06-23T05:54:24.785Z",
            "numAgents": 4,
            "ancestors": []
        },
        {
            "_id": "4LCeYmCHHnQ3EDBgf",
            "enabled": true,
            "name": "Chatbot Sales",
            "description": "",
            "showOnRegistration": false,
            "showOnOfflineForm": false,
            "requestTagBeforeClosingChat": false,
            "email": "",
            "chatClosingTags": [],
            "offlineMessageChannelName": "",
            "abandonedRoomsCloseCustomMessage": "",
            "waitingQueueMessage": "",
            "departmentsAllowedToForward": "",
            "_updatedAt": "2021-06-23T06:02:09.321Z",
            "numAgents": 3,
            "ancestors": []
        },
        {
            "_id": "mHcx4rbi7htAmCCR5",
            "enabled": true,
            "name": "Chatbot Support",
            "description": "",
            "showOnRegistration": false,
            "showOnOfflineForm": false,
            "requestTagBeforeClosingChat": false,
            "email": "",
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
        },
        {
            "_id": "qBXjxBekDEiZjftRZ",
            "enabled": false,
            "name": "Luis's Test",
            "description": "",
            "showOnRegistration": false,
            "showOnOfflineForm": false,
            "requestTagBeforeClosingChat": false,
            "email": "",
            "chatClosingTags": [],
            "offlineMessageChannelName": "",
            "abandonedRoomsCloseCustomMessage": "",
            "waitingQueueMessage": "",
            "departmentsAllowedToForward": "",
            "_updatedAt": "2021-06-23T05:54:04.198Z",
            "numAgents": 1
        },
        {
            "_id": "J2BwLM9qWWz5CDuSY",
            "enabled": false,
            "name": "testing a long department text - this will be deleted afterwards",
            "description": "",
            "showOnRegistration": false,
            "showOnOfflineForm": false,
            "requestTagBeforeClosingChat": false,
            "email": "",
            "chatClosingTags": [],
            "offlineMessageChannelName": "",
            "abandonedRoomsCloseCustomMessage": "",
            "waitingQueueMessage": "",
            "departmentsAllowedToForward": "",
            "_updatedAt": "2021-06-18T18:02:13.263Z",
            "numAgents": 1,
            "ancestors": []
        },
        {
            "_id": "Pb8oBxSEwgWasnxX6",
            "enabled": true,
            "name": "José",
            "description": "let´s test offline livechat",
            "showOnRegistration": false,
            "showOnOfflineForm": false,
            "requestTagBeforeClosingChat": false,
            "email": "",
            "chatClosingTags": [],
            "offlineMessageChannelName": "",
            "abandonedRoomsCloseCustomMessage": "",
            "waitingQueueMessage": "please wait",
            "departmentsAllowedToForward": "",
            "_updatedAt": "2021-06-23T05:57:12.758Z",
            "numAgents": 1
        }
    ],
    "count": 15,
    "offset": 0,
    "total": 15,
    "success": true
}
```

## Change Log
