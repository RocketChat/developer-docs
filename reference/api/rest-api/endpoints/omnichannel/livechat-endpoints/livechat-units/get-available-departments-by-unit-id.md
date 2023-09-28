# Get Available Departments by Unit Id

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

<table><thead><tr><th width="378.3333333333333">URL</th><th>Requires Auth</th><th>HTTP Method</th></tr></thead><tbody><tr><td><code>api/v1/livechat/units/:unitId/departments/available</code></td><td><code>YES</code></td><td><code>GET</code></td></tr></tbody></table>

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
curl --location --request GET 'http://localhost:3000/api/v1/livechat/units/TGjc7wN84KxQup9cF/departments/available' \
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
            "visitorInactivityTimeoutInSeconds": "",
        }
    ],
    "count": 2,
    "offset": 0,
    "total": 2,
    "success": true
}
```
