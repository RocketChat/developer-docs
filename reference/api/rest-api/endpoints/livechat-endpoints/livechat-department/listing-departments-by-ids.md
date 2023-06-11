---
description: Retrieves a list of departments by array of department ids
---

# Listing departments by ids

| URL                                    | Requires Auth | HTTP Method |
| -------------------------------------- | ------------- | ----------- |
| `api/v1/livechat/department.listByIds` | `YES`         | `GET`       |

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Query Parameters

| Argument | Example             | Required |               |
| -------- | ------------------- | -------- | ------------- |
| `ids`    | `4LCeYmCHHnQ3EDBgf` | Required | Department id |
| `ids`    | `CAJioQNAvLnYWTy8i` | Required | Department id |
| `ids`    | `mHcx4rbi7htAmCCR5` | Optional | Department id |

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/livechat/department.listByIds?ids=4LCeYmCHHnQ3EDBgf&ids=CAJioQNAvLnYWTy8i&ids=mHcx4rbi7htAmCCR5\
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript
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
