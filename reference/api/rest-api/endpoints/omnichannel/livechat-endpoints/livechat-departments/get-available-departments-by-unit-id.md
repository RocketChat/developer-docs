# Get Available Departments by Unit ID

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Gives departments that have not been associated to another unit yet.

{% hint style="warning" %}
![](../../../../../../../.gitbook/assets/Deprecated.png) This endpoint has been renamed to [get-available-departments-by-unit-id.md](../livechat-units/get-available-departments-by-unit-id.md "mention") from Rocket.Chat `5.0`
{% endhint %}

<table><thead><tr><th width="163">HTTP Method</th><th width="305">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>api/v1/livechat/departments.available-by-unit/:unitId</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Path Variables

<table><thead><tr><th width="217.33333333333331">Key</th><th>Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>unitId</code><mark style="color:red;"><code>*</code></mark></td><td><code>sriw2wmP2Zz2pPrre</code></td><td>The unit ID.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```bash
curl --location --request GET 'http://localhost:3000///api/v1/livechat/departments.available-by-unit/:unitId \
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
        }
    ],
    "count": 4,
    "offset": 0,
    "total": 4,
    "success": true
}
```
