# Get Livechat Appearance

Get the settings about the widget appearance.

<table><thead><tr><th width="163">HTTP Method</th><th width="304">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/livechat/appearance</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `view-livechat-manager`
{% endhint %}

## Example Call

```powershell
curl -L -X GET 'http://localhost:3000/api/v1/livechat/appearance' \
-H 'x-auth-token: qlHA60g5JQjJJG7C_8MgXoFnOiRQ8X9TWVVq4AcQeFb' \
-H 'x-user-id: rbAXPnMktTFbNpwtJ'
```

## Example Response

```json
{
    "appearance": [
        {
            "_id": "Livechat_conversation_finished_message",
            "type": "string",
            "group": "Omnichannel",
            "public": true,
            "i18nLabel": "Conversation_finished_message",
            "packageValue": "",
            "valueSource": "packageValue",
            "hidden": false,
            "blocked": false,
            "sorter": 16,
            "i18nDescription": "Livechat_conversation_finished_message_Description",
            "autocomplete": true,
            "ts": "2021-12-03T16:21:59.851Z",
            "_updatedAt": "2021-12-03T16:21:59.851Z",
            "createdAt": "2021-12-03T16:21:59.851Z",
            "value": "CLOSE!!!",
            "secret": false,
            "section": "Livechat",
            "enterprise": false,
            "requiredOnWizard": false,
            "env": false,
            "enableQuery": "{\"_id\":\"Livechat_enabled\",\"value\":true}"
        },
        {
            "_id": "Livechat_conversation_finished_text",
            "_updatedAt": "2023-02-06T17:25:35.940Z",
            "autocomplete": true,
            "blocked": false,
            "createdAt": "2021-12-03T16:21:59.861Z",
            "group": "Omnichannel",
            "hidden": false,
            "i18nDescription": "Livechat_conversation_finished_text_Description",
            "i18nLabel": "Conversation_finished_text",
            "multiline": true,
            "packageValue": "",
            "public": true,
            "secret": false,
            "sorter": 17,
            "ts": "2021-12-03T16:21:59.861Z",
            "type": "string",
            "value": "BYE!!!",
            "valueSource": "packageValue",
            "section": "Livechat",
            "enterprise": false,
            "requiredOnWizard": false,
            "env": false,
            "enableQuery": "{\"_id\":\"Livechat_enabled\",\"value\":true}"
        },
        {
            "_id": "Livechat_display_offline_form",
            "type": "boolean",
            "group": "Omnichannel",
            "public": true,
            "section": "Livechat",
            "i18nLabel": "Display_offline_form",
            "packageValue": true,
            "valueSource": "packageValue",
            "hidden": false,
            "blocked": false,
            "sorter": 4,
            "i18nDescription": "Livechat_display_offline_form_Description",
            "ts": "2021-10-27T22:25:42.892Z",
            "_updatedAt": "2021-10-27T22:25:42.892Z",
            "createdAt": "2021-10-27T22:25:42.892Z",
            "value": true,
            "autocomplete": true,
            "secret": false,
            "enterprise": false,
            "requiredOnWizard": false,
            "env": false,
            "enableQuery": "{\"_id\":\"Livechat_enabled\",\"value\":true}"
        },
	...
        {
            "_id": "Livechat_email_field_registration_form",
            "type": "boolean",
            "group": "Omnichannel",
            "public": true,
            "i18nLabel": "Show_email_field",
            "packageValue": true,
            "valueSource": "packageValue",
            "hidden": false,
            "blocked": false,
            "sorter": 20,
            "i18nDescription": "Livechat_email_field_registration_form_Description",
            "autocomplete": true,
            "ts": "2021-12-03T16:21:59.926Z",
            "_updatedAt": "2021-12-03T16:21:59.926Z",
            "createdAt": "2021-12-03T16:21:59.926Z",
            "value": true,
            "secret": false,
            "section": "Livechat",
            "enterprise": false,
            "requiredOnWizard": false,
            "env": false,
            "enableQuery": "{\"_id\":\"Livechat_enabled\",\"value\":true}"
        },

        {
            "_id": "Livechat_show_agent_info",
            "_updatedAt": "2023-08-10T13:27:26.422Z",
            "autocomplete": true,
            "blocked": false,
            "createdAt": "2021-12-03T16:21:59.833Z",
            "group": "Omnichannel",
            "hidden": false,
            "i18nDescription": "Livechat_show_agent_info_Description",
            "i18nLabel": "Show_agent_info",
            "packageValue": true,
            "public": true,
            "secret": false,
            "sorter": 14,
            "ts": "2021-12-03T16:21:59.833Z",
            "type": "boolean",
            "value": false,
            "valueSource": "packageValue",
            "section": "Livechat",
            "enterprise": false,
            "requiredOnWizard": false,
            "env": false,
            "enableQuery": "{\"_id\":\"Livechat_enabled\",\"value\":true}"
        },
	.....
        {
            "_id": "Livechat_title",
            "type": "string",
            "group": "Omnichannel",
            "public": true,
            "packageValue": "Rocket.Chat",
            "valueSource": "packageValue",
            "hidden": false,
            "blocked": false,
            "sorter": 0,
            "i18nLabel": "Livechat_title",
            "i18nDescription": "Livechat_title_Description",
            "ts": "2021-10-27T22:25:42.874Z",
            "_updatedAt": "2023-09-01T17:17:39.628Z",
            "createdAt": "2021-10-27T22:25:42.874Z",
            "value": "Hello",
            "autocomplete": true,
            "secret": false,
            "section": "Livechat",
            "enterprise": false,
            "requiredOnWizard": false,
            "env": false,
            "enableQuery": "{\"_id\":\"Livechat_enabled\",\"value\":true}"
        },
        {
            "_id": "Livechat_title_color",
            "type": "color",
            "group": "Omnichannel",
            "public": true,
            "packageValue": "#C1272D",
            "valueSource": "packageValue",
            "hidden": false,
            "blocked": false,
            "sorter": 1,
            "i18nLabel": "Livechat_title_color",
            "i18nDescription": "Livechat_title_color_Description",
            "ts": "2021-10-27T22:25:42.882Z",
            "_updatedAt": "2023-03-30T12:19:01.124Z",
            "createdAt": "2021-10-27T22:25:42.882Z",
            "value": "#b427be",
            "autocomplete": true,
            "editor": "color",
            "secret": false,
            "section": "Livechat",
            "enterprise": false,
            "requiredOnWizard": false,
            "env": false,
            "packageEditor": "color",
            "enableQuery": "{\"_id\":\"Livechat_enabled\",\"value\":true}"
        }
    ],
    "success": true
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 6.4.0   | Added       |
