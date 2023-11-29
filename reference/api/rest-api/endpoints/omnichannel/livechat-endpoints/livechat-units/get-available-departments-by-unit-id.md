# Get Available Departments by Unit Id

<figure><img src="../../../../../../../.gitbook/assets/Premium.svg" alt=""><figcaption></figcaption></figure>

Gets all the available departments.

<table><thead><tr><th width="163">HTTP Method</th><th width="332">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/units/:unitId/departments/available</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `manage-livechat-units`
{% endhint %}

## Path Variables

<table><thead><tr><th width="211.33333333333331">Key</th><th width="253">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>unitId</code><mark style="color:red;"><code>*</code></mark></td><td><code>sriw2wmP2Zz2pPrre</code></td><td>The unit ID.</td></tr></tbody></table>

## Query Parameters

This endpoint supports the optional `count` and `offset` [#pagination](../../../../#pagination "mention") parameters. Additional optional parameters are as follows:

<table><thead><tr><th width="220.33333333333331">Key</th><th width="195">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>text</code></td><td><code>test</code></td><td>The text with which you want to filter the result.</td></tr><tr><td><code>onlyMyDepartments</code></td><td><code>true</code></td><td>Displays the departments that you are part of.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request GET 'http://localhost:3000/api/v1/livechat/units/TGjc7wN84KxQup9cF/departments/available' \
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
            "visitorInactivityTimeoutInSeconds": "",
        }
    ],
    "count": 2,
    "offset": 0,
    "total": 2,
    "success": true
}
```
