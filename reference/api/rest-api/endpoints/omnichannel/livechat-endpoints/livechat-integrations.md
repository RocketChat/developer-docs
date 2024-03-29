---
description: Retrieves a list of integration settings.
---

# Get Livechat Integrations

Retrieves a list of integration settings.

<table><thead><tr><th width="163">HTTP Method</th><th width="332">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/integrations.settings</code></td><td><a href="../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `view-livechat-manager`
{% endhint %}

## Example Call

```powershell
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     http://localhost:3000/api/v1/livechat/integrations.settings
```

## Example Response

```json
{
    "settings": [
        {
            "_id": "Livechat_secret_token",
            "_updatedAt": "2019-10-17T13:56:07.285Z",
            "autocomplete": true,
            "blocked": false,
            "createdAt": "2019-10-07T18:52:20.484Z",
            "group": "Livechat",
            "hidden": false,
            "i18nDescription": "Livechat_secret_token_Description",
            "i18nLabel": "Secret_token",
            "packageValue": "",
            "secret": true,
            "section": "CRM_Integration",
            "sorter": 25,
            "ts": "2019-10-07T21:00:01.287Z",
            "type": "string",
            "value": "",
            "valueSource": "meteorSettingsValue",
            "meteorSettingsValue": ""
        }
    ],
    "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 2.2.0   | Added       |
