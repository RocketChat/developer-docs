# Get List of Departments

Get a list of the departments.

<table><thead><tr><th width="163">HTTP Method</th><th width="305">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/department</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Query Parameters

This endpoint supports the [#pagination](../../../../#pagination "mention") parameters. Additional optional query parameters are as follows:

<table><thead><tr><th width="241">Key</th><th width="201">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>text</code></td><td><code>fin</code></td><td>Filter the result with any text.</td></tr><tr><td><code>enabled</code></td><td><code>true</code></td><td>Filter the result to only show enabled departments. The value can be boolean <code>true</code> or <code>false</code>.</td></tr><tr><td><code>showArchived</code></td><td><code>true</code></td><td>You can include the archived departments in the result. The value can be boolean <code>true</code> or <code>false</code>.</td></tr><tr><td><code>onlyMyDepartments</code></td><td><code>true</code></td><td>This parameter is for users with managers or admin roles. It only displays the departments that you are an agent of.</td></tr><tr><td><code>excludeDepartmentId</code></td><td><code>64181a0728384134ed600dcc</code></td><td>The department ID that you want to exclude from the result.</td></tr></tbody></table>

## Example Call

```powershell
curl --location 'http://localhost:3000/api/v1/livechat/department' \
--header 'X-Auth-Token: Y97tM4GkYjgaH_fIO5dwBitQ' \
--header 'X-User-Id: CkCPNcvsvCDfmWLqC' \
--data ''
```

## Example Response

```json
{
    "departments": [
        {
            "_id": "64181a0728384134ed600dcc",
            "enabled": true,
            "name": "Support",
            "description": "",
            "showOnRegistration": false,
            "showOnOfflineForm": false,
            "requestTagBeforeClosingChat": false,
            "email": "kim.jane@rocketchat.com",
            "chatClosingTags": [],
            "offlineMessageChannelName": "Livestream",
            "abandonedRoomsCloseCustomMessage": "",
            "waitingQueueMessage": "",
            "departmentsAllowedToForward": [],
            "fallbackForwardDepartment": "",
            "_updatedAt": "2023-10-13T13:03:58.406Z",
            "numAgents": 4,
            "type": "d"
        },
        {
            "_id": "649230d479f5c6e276cf4a12",
            "enabled": false,
            "name": "Finance",
            "description": "",
            "showOnRegistration": false,
            "showOnOfflineForm": false,
            "requestTagBeforeClosingChat": false,
            "email": "test@gmail.com",
            "chatClosingTags": [],
            "offlineMessageChannelName": "",
            "abandonedRoomsCloseCustomMessage": "",
            "waitingQueueMessage": "",
            "departmentsAllowedToForward": [],
            "fallbackForwardDepartment": "",
            "type": "d",
            "_updatedAt": "2023-10-13T13:03:58.426Z",
            "numAgents": 3,
            "businessHourId": "650dc9cfa2f73c7460e18bea"
        }
    ],
    "count": 2,
    "offset": 0,
    "total": 2,
    "success": true
}
```

## Change Log

| Version | Description                 |
| ------- | --------------------------- |
| 2.2.0   | Added support to pagination |
| 0.42.0  | Added                       |
