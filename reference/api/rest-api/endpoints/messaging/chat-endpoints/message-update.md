# Message Update

| URL                   | Requires Auth | HTTP Method |
| --------------------- | ------------- | ----------- |
| `/api/v1/chat.update` | `yes`         | `POST`      |

## Payload

<table><thead><tr><th width="173">Argument</th><th>Example</th><th width="133">Required</th><th>Description</th></tr></thead><tbody><tr><td><code>roomId</code></td><td><code>ByehQjC44FwMeiLbX</code></td><td>Required</td><td>The room id of where the message is.</td></tr><tr><td><code>msgId</code></td><td><code>7aDSXtjMA3KPLxLjt</code></td><td>Required</td><td>The message id to update.</td></tr><tr><td><code>text</code></td><td><code>Updated text</code></td><td>Required</td><td>Updated text for the message.</td></tr><tr><td><code>previewUrls</code></td><td><p><code>[ "https://google.com", "https://writing-demo.dev.rocket.chat"</code></p><p><code>]</code></p></td><td>Optional</td><td>An array to define which URL previews should be retrieved from each message.</td></tr><tr><td><code>customFields</code></td><td><code>{"priority": "high"}</code></td><td>Optional</td><td>You can add custom fields for messages. For example, set priorities for messages.<br><br>You must enable this option and define the validation in the workspace settings. See the <a href="https://docs.rocket.chat/use-rocket.chat/workspace-administration/settings/message">Message</a> settings for further information.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```bash
curl -L -X POST 'http://localhost:3000/api/v1/chat.update' \
-H 'x-auth-token: wrhSO31BO6Zn6G5Aa_bj-kMmImONHDjXrOwGtBpQIPM' \
-H 'x-user-id: rbAXPnMktTFbNpwtJ' \
-H 'Content-Type: application/json' \
-d '{
   "roomId":"64f0f82c2c26843a68c1f7ba",
   "msgId":"vzGBzSwy6jJQDwtZe",
   "text":"Updated list of links! https://google.com https://hola.org/ https://www.usepayday.com/ https://www.getbumpa.com/ https://www.atlassian.com/software/jira https://writing-demo.dev.rocket.chat",
   "previewUrls":[
      "https://google.com",
      "https://writing-demo.dev.rocket.chat"

   ]
}'
```
{% endcode %}

## Example Result

{% code overflow="wrap" fullWidth="false" %}
```json
{
    "message": {
        "_id": "vzGBzSwy6jJQDwtZe",
        "rid": `"64f0f82c2c26843a68c1f7ba",
        "msg": "Updated list of links! https://google.com https://hola.org/ https://www.usepayday.com/ https://www.getbumpa.com/ https://www.atlassian.com/software/jira https://writing-demo.dev.rocket.chat",
        "ts": "2023-09-20T17:27:59.945Z",
        "u": {
            "_id": "rbAXPnMktTFbNpwtJ",
            "username": "roxie",
            "name": "Funke Olasupo"
        },
        "_updatedAt": "2023-09-20T22:22:45.793Z",
        "urls": [
            {
                "url": "https://google.com",
                "meta": {}
            },
            {
                "url": "https://hola.org/",
                "meta": {},
                "ignoreParse": true
            },
            {
                "url": "https://www.usepayday.com/",
                "meta": {},
                "ignoreParse": true
            },
            {
                "url": "https://www.getbumpa.com/",
                "meta": {},
                "ignoreParse": true
            },
            {
                "url": "https://www.atlassian.com/software/jira",
                "meta": {},
                "ignoreParse": true
            },
            {
                "url": "https://writing-demo.dev.rocket.chat",
                "meta": {}
            }
        ],
        "mentions": [],
        "channels": [],
        "md": [
            {
                "type": "PARAGRAPH",
                "value": [
                    {
                        "type": "PLAIN_TEXT",
                        "value": "Updated list of links! "
                    },
                    {
                        "type": "LINK",
                        "value": {
                            "src": {
                                "type": "PLAIN_TEXT",
                                "value": "https://google.com"
                            },
                            "label": [
                                {
                                    "type": "PLAIN_TEXT",
                                    "value": "https://google.com"
                                }
                            ]
                        }
                    },
                    {
                        "type": "PLAIN_TEXT",
                        "value": " "
                    },
                    {
                        "type": "LINK",
                        "value": {
                            "src": {
                                "type": "PLAIN_TEXT",
                                "value": "https://hola.org/"
                            },
                            "label": [
                                {
                                    "type": "PLAIN_TEXT",
                                    "value": "https://hola.org/"
                                }
                            ]
                        }
                    },
                    {
                        "type": "PLAIN_TEXT",
                        "value": " "
                    },
                    {
                        "type": "LINK",
                        "value": {
                            "src": {
                                "type": "PLAIN_TEXT",
                                "value": "https://www.usepayday.com/"
                            },
                            "label": [
                                {
                                    "type": "PLAIN_TEXT",
                                    "value": "https://www.usepayday.com/"
                                }
                            ]
                        }
                    },
                    {
                        "type": "PLAIN_TEXT",
                        "value": " "
                    },
                    {
                        "type": "LINK",
                        "value": {
                            "src": {
                                "type": "PLAIN_TEXT",
                                "value": "https://www.getbumpa.com/"
                            },
                            "label": [
                                {
                                    "type": "PLAIN_TEXT",
                                    "value": "https://www.getbumpa.com/"
                                }
                            ]
                        }
                    },
                    {
                        "type": "PLAIN_TEXT",
                        "value": " "
                    },
                    {
                        "type": "LINK",
                        "value": {
                            "src": {
                                "type": "PLAIN_TEXT",
                                "value": "https://www.atlassian.com/software/jira"
                            },
                            "label": [
                                {
                                    "type": "PLAIN_TEXT",
                                    "value": "https://www.atlassian.com/software/jira"
                                }
                            ]
                        }
                    },
                    {
                        "type": "PLAIN_TEXT",
                        "value": " "
                    },
                    {
                        "type": "LINK",
                        "value": {
                            "src": {
                                "type": "PLAIN_TEXT",
                                "value": "https://writing-demo.dev.rocket.chat"
                            },
                            "label": [
                                {
                                    "type": "PLAIN_TEXT",
                                    "value": "https://writing-demo.dev.rocket.chat"
                                }
                            ]
                        }
                    }
                ]
            }
        ],
        "editedAt": "2023-09-20T22:22:45.737Z",
        "editedBy": {
            "_id": "rbAXPnMktTFbNpwtJ",
            "username": "roxie"
        }
    },
    "success": true
}`
```
{% endcode %}

## Change Log

| Version | Description             |
| ------- | ----------------------- |
| 0.49.0  | Added                   |
| 6.4.0   | Add `previewUrls` param |
