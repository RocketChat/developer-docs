# Get Department by Unit Id

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Gives departments included in a specific unit id

<table><thead><tr><th width="463.3333333333333">URL</th><th>Requires Auth</th><th>HTTP Method</th></tr></thead><tbody><tr><td><code>api/v1/livechat/units/:unitId/departments</code></td><td><code>YES</code></td><td><code>GET</code></td></tr></tbody></table>

## Headers

| Argument       | Example        | Required | Description                                                    |
| -------------- | -------------- | -------- | -------------------------------------------------------------- |
| `X-User-Id`    | `myuser-name`  | Required | Your username hash (returned after you log in through the API) |
| `X-Auth-Token` | `myauth-token` | Required | Your token (returned after you log in through the API)         |

## Path Variables

<table><thead><tr><th>Argument</th><th width="227">Example</th><th>Required</th><th>Description</th></tr></thead><tbody><tr><td><code>unitId</code></td><td><code>sriw2wmP2Zz2pPrre</code></td><td>Required</td><td>Unit Id</td></tr></tbody></table>

## Example Call

```bash
curl --location --request GET 'http://localhost:3000/api/v1/livechat/units/TGjc7wN84KxQup9cF/departments' \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```

## Result

```javascript
{
    "departments": [
        {
            "_id": "MfvRXBwEWY6tTwqFh",
            "enabled": true,
            "name": "C",
            "description": "test dept",
            "showOnRegistration": true,
            "showOnOfflineForm": true,
            "requestTagBeforeClosingChat": true,
            "email": "C@test.com",
            "chatClosingTags": [
                "please add a tag"
            ],
            "offlineMessageChannelName": "",
            "maxNumberSimultaneousChat": "2",
            "visitorInactivityTimeoutInSeconds": "0",
            "abandonedRoomsCloseCustomMessage": "closed",
            "waitingQueueMessage": "please wait!",
            "departmentsAllowedToForward": "",
            "_updatedAt": "2022-12-14T14:44:51.923Z",
            "numAgents": 5,
            "ancestors": [
                "TGjc7wN84KxQup9cF"
            ],
            "parentId": "TGjc7wN84KxQup9cF",
            "fallbackForwardDepartment": "KgCzEB2gWngKp9JF3"
        }
    ],
    "count": 1,
    "offset": 0,
    "total": 1,
    "success": true
}
```
