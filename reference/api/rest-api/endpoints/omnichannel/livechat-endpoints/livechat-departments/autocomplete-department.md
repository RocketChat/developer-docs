# Autocomplete Department

Autocomplete the department name.

<table><thead><tr><th width="163">HTTP Method</th><th width="305">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/department.autocomplete</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permissions required:

* `view-livechat-departments`
* `view-l-room`
{% endhint %}

## Query Parameters

<table><thead><tr><th width="225">Key</th><th width="230.33333333333331">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>selector</code><mark style="color:red;"><code>*</code></mark></td><td><code>{ "exceptions" : [], "conditions" : {}}</code></td><td>Enter the exceptions or the conditions that you want to search for.</td></tr><tr><td><code>onlyMyDepartments</code></td><td><code>true</code></td><td>Only displays the departments that you are assigned to. The value can be boolean <code>true</code> or <code>false</code>.</td></tr><tr><td><code>showArchived</code></td><td><code>true</code></td><td>The result includes archived departments. The value can be boolean <code>true</code> or <code>false</code>.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request GET 'http://localhost:3000/api/v1/livechat/department.autocomplete?selector={} \
--header 'X-Auth-Token: myauth-token' \
--header 'X-User-Id: myuser-name'
```
{% endcode %}

## Example Response

```json
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
            "email": "brazil@rocketchat.com",
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
            "email": "br@rocketchat.com",
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
        }
    ],
    "count": 2,
    "offset": 0,
    "total": 2,
    "success": true
}
```
