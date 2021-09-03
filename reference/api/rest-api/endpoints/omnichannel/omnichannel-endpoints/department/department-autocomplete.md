---
description: Autocompletes department name
---

# Department autocomplete

| URL | Requires Auth | HTTP Method |
| :--- | :--- | :--- |
| `api/v1/livechat/department.autocomplete` | `YES` | `GET` |

## Headers

| Argument | Example | Required | Description |
| :--- | :--- | :--- | :--- |
| `X-User-Id` | `myuser-name` | Required | Your username hash \(returned after you log in through the API\) |
| `X-Auth-Token` | `myauth-token` | Required | Your token \(returned after you log in through the API\) |

## Parameters

| Argument | Example | Required |
| :--- | :--- | :--- |
| `text` |  | Required |
| `onlyMyDepartments` | `true` | Required |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/livechat/department?text=&onlyMyDepartments=true \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript
{
    "departments": [
        {
            "_id": "qajzu7WaBRoQBpq6Z",
            "enabled": true,
            "name": "Brazil",
            "description": "",
            "numAgents": 3,
            "showOnRegistration": false,
            "showOnOfflineForm": true,
            "email": "brazil@rocket.chat",
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
            "_id": "NhnC9dBwFonZqSQ5m",
            "enabled": true,
            "name": "CSM and Support",
            "description": "",
            "showOnRegistration": true,
            "showOnOfflineForm": false,
            "requestTagBeforeClosingChat": false,
            "email": "br@rocket.chat",
            "chatClosingTags": [],
            "offlineMessageChannelName": "",
            "abandonedRoomsCloseCustomMessage": "",
            "waitingQueueMessage": "",
            "departmentsAllowedToForward": [
                "CAJioQNAvLnYWTy8i",
                "Z2KWYBJQFR7AzfmQL"
            ],
            "_updatedAt": "2021-07-12T18:05:53.257Z",
            "numAgents": 4
        },
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
            "_id": "Yi87Ju7eTHiZQ7CJt",
            "enabled": false,
            "name": "Customer Success",
            "description": "TEST",
            "showOnRegistration": false,
            "showOnOfflineForm": true,
            "requestTagBeforeClosingChat": false,
            "email": "rogera@rocket.chat",
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
            "_id": "8MGLTfaKLCbE9CqR8",
            "enabled": false,
            "name": "Demo",
            "description": "",
            "showOnRegistration": false,
            "showOnOfflineForm": false,
            "requestTagBeforeClosingChat": false,
            "email": "mo@rocket.chat",
            "chatClosingTags": [],
            "offlineMessageChannelName": "",
            "maxNumberSimultaneousChat": "",
            "visitorInactivityTimeoutInSeconds": "",
            "abandonedRoomsCloseCustomMessage": "",
            "waitingQueueMessage": "",
            "departmentsAllowedToForward": "",
            "_updatedAt": "2021-07-09T04:49:30.501Z",
            "numAgents": 7,
            "ancestors": []
        },
        {
            "_id": "BiqbQav59HD2LzXEY",
            "enabled": true,
            "name": "Experimental - Talk to a chatbot",
            "description": "",
            "showOnRegistration": true,
            "showOnOfflineForm": true,
            "requestTagBeforeClosingChat": false,
            "email": "sup@rocket.chat",
            "chatClosingTags": [],
            "offlineMessageChannelName": "",
            "maxNumberSimultaneousChat": "3",
            "visitorInactivityTimeoutInSeconds": "",
            "abandonedRoomsCloseCustomMessage": "",
            "waitingQueueMessage": "",
            "departmentsAllowedToForward": "",
            "type": "d",
            "numAgents": 1,
            "_updatedAt": "2021-07-14T14:58:00.993Z",
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
            "email": "@rocket.chat",
            "chatClosingTags": [],
            "offlineMessageChannelName": "",
            "abandonedRoomsCloseCustomMessage": "",
            "waitingQueueMessage": "please wait",
            "departmentsAllowedToForward": "",
            "_updatedAt": "2021-06-23T05:57:12.758Z",
            "numAgents": 1
        },
        {
            "_id": "qBXjxBekDEiZjftRZ",
            "enabled": false,
            "name": "Luis's Test",
            "description": "",
            "showOnRegistration": false,
            "showOnOfflineForm": false,
            "requestTagBeforeClosingChat": false,
            "email": "luis@rocket.chat",
            "chatClosingTags": [],
            "offlineMessageChannelName": "",
            "abandonedRoomsCloseCustomMessage": "",
            "waitingQueueMessage": "",
            "departmentsAllowedToForward": "",
            "_updatedAt": "2021-06-23T05:54:04.198Z",
            "numAgents": 1
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
            "_id": "GaA9kDdnxdFJtj5hi",
            "enabled": true,
            "name": "Offline Department",
            "description": "",
            "showOnRegistration": false,
            "showOnOfflineForm": false,
            "requestTagBeforeClosingChat": false,
            "email": "OfflineDepartment@g.c",
            "chatClosingTags": [],
            "offlineMessageChannelName": "",
            "abandonedRoomsCloseCustomMessage": "",
            "waitingQueueMessage": "",
            "departmentsAllowedToForward": "",
            "_updatedAt": "2021-07-09T07:02:00.614Z",
            "numAgents": 1
        },
        {
            "_id": "GgYvrkAF63aeQmsh4",
            "enabled": true,
            "name": "Sales",
            "description": "For sales purposes only, we are happy to help",
            "showOnRegistration": true,
            "showOnOfflineForm": true,
            "requestTagBeforeClosingChat": true,
            "email": "daniel.townsend@rocket.chat",
            "chatClosingTags": [
                "Junk lead",
                "Valuable lead"
            ],
            "maxNumberSimultaneousChat": "",
            "waitingQueueMessage": "",
            "type": "d",
            "numAgents": 22,
            "_updatedAt": "2021-07-13T16:13:12.028Z",
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
            "_id": "sLYp3ry7CRizaP3rJ",
            "enabled": false,
            "name": "Sales test",
            "description": "Sales test",
            "showOnRegistration": false,
            "showOnOfflineForm": false,
            "requestTagBeforeClosingChat": false,
            "email": "jose@rocket.chat",
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
            "_id": "CAJioQNAvLnYWTy8i",
            "enabled": true,
            "name": "Support",
            "description": "",
            "showOnRegistration": true,
            "showOnOfflineForm": true,
            "requestTagBeforeClosingChat": false,
            "email": "maryna@rocket.chat",
            "maxNumberSimultaneousChat": "",
            "waitingQueueMessage": "",
            "type": "d",
            "numAgents": 26,
            "_updatedAt": "2021-07-16T23:47:55.961Z",
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
            "email": "karina@rocket.chat",
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
            "_id": "J2BwLM9qWWz5CDuSY",
            "enabled": false,
            "name": "testing a long department text - this will be deleted afterwards",
            "description": "",
            "showOnRegistration": false,
            "showOnOfflineForm": false,
            "requestTagBeforeClosingChat": false,
            "email": "rey@rocket.chat",
            "chatClosingTags": [],
            "offlineMessageChannelName": "",
            "abandonedRoomsCloseCustomMessage": "",
            "waitingQueueMessage": "",
            "departmentsAllowedToForward": "",
            "_updatedAt": "2021-06-18T18:02:13.263Z",
            "numAgents": 1,
            "ancestors": []
        }
    ],
    "count": 17,
    "offset": 0,
    "total": 17,
    "success": true
}
```

