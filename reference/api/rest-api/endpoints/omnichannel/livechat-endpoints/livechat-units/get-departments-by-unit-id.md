# Get Departments by Unit Id

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Gives departments included in a specific unit ID.

<table><thead><tr><th width="163">HTTP Method</th><th width="332">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/units/:unitId/departments</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `manage-livechat-units`
{% endhint %}

## Path Variables

<table><thead><tr><th width="210">Key</th><th width="230">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>unitId</code><mark style="color:red;"><code>*</code></mark></td><td><code>sriw2wmP2Zz2pPrre</code></td><td>The unit ID.</td></tr></tbody></table>

## Query Parameters

This endpoint supports the optional `count` and `offset` [#pagination](../../../../#pagination "mention") parameters.

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request GET 'http://localhost:3000/api/v1/livechat/units/TGjc7wN84KxQup9cF/departments' \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```
{% endcode %}

## Example Response

```json
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
