# Get Livechat Configurations

Get Livechat widget configuration information and additional visitor data.

<table><thead><tr><th width="163">HTTP Method</th><th width="338">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/config</code></td><td><code>no</code></td></tr></tbody></table>

## Query Parameters

<table><thead><tr><th width="208.33333333333331">Key</th><th width="241">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>token</code></td><td><code>iNKE8a6k6cjbqWhWd</code></td><td>The visitor <code>token</code>.</td></tr><tr><td><code>department</code></td><td><code>department</code></td><td>The visitor's <code>department</code>.</td></tr></tbody></table>

## Example Calls

Without query parameters:

```powershell
curl --location 'http://localhost:3000/api/v1/livechat/config'
```

With query parameters:

```powershell
curl --location 'http://localhost:3000/api/v1/livechat/config?token=iNKE8a6k6cjbqWhWd'
curl --location 'http://localhost:3000/api/v1/livechat/config?department=department'
```

## Example Response

```json
{
  "config": {
    "enabled": true,
    "settings": {
      "registrationForm": true,
      "allowSwitchingDepartments": false,
      "nameFieldRegistrationForm": true,
      "emailFieldRegistrationForm": true,
      "displayOfflineForm": true,
      "videoCall": false,
      "fileUpload": true,
      "language": "",
      "transcript": false,
      "historyMonitorType": "url",
      "forceAcceptDataProcessingConsent": false,
      "showConnecting": true,
      "agentHiddenInfo": false,
      "clearLocalStorageWhenChatEnded": false,
      "limitTextLength": false
    },
    "theme": {
      "title": "Rocket.Chat",
      "color": "#C1272D",
      "offlineTitle": "Leave a message",
      "offlineColor": "#666666",
      "actionLinks": [{
          "icon": "icon-videocam",
          "i18nLabel": "Accept",
          "method_id": "createLivechatCall",
          "params": ""
        },
        {
          "icon": "icon-cancel",
          "i18nLabel": "Decline",
          "method_id": "denyLivechatCall",
          "params": ""
        }
      ],
    },
    "messages": {
      "offlineMessage": "",
      "offlineSuccessMessage": "",
      "offlineUnavailableMessage": "",
      "conversationFinishedMessage": "",
      "transcriptMessage": ""
    },
    "survey": {
      "items": [
        "satisfaction",
        "agentKnowledge",
        "agentResposiveness",
        "agentFriendliness"
      ],
      "values": [
        "1",
        "2",
        "3",
        "4",
        "5"
      ],
    },
    "departments": [
    {
        "_id": "64cf6c6feb07a913d946f34d",
        "name": "Test",
        "showOnRegistration": false,
        "showOnOfflineForm": false
     },
     {
        "_id": "6523ff86a2f73c7460e18d6d",
        "name": "Dept-011",
        "showOnRegistration": false,
        "showOnOfflineForm": true
      },
      {
         "_id": "652882d8a2f73c7460e18dc4",
         "name": "Support",
         "showOnRegistration": false,
         "showOnOfflineForm": false
       },
       {
          "_id": "64181a0728384134ed600dcc",
          "name": "Lost",
          "showOnRegistration": false,
          "showOnOfflineForm": false
        }
        ],
    "online": true,
    "guest": {
      "_id": "2KNu66RPCwxA4ncy7",
      "username": "guest-3",
      "token": "iNKE8a6k6cjbqWhWd",
      "name": "Livechat Visitor"
    },
    "room": {
      "_id": "zRAeTszXor8CCPceB",
      "servedBy": {
        "_id": "7Gm3PoFCJWTCJ68XR",
        "username": "livechat.agent"
      },
      "open": true
    },
    "agent": {
      "_id": "7Gm3PoFCJWTCJ68XR",
      "emails": [{
        "address": "agent@rocket.chat",
        "verified": true
      }],
      "name": "Livechat Agent",
      "username": "livechat.agent"
    }
  },
  "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.70.0  | Added       |
