# Set Livechat Appearance

Update [livechat widget appearance](https://docs.rocket.chat/use-rocket.chat/omnichannel/livechat-widget-appearance) settings.

| URL                           | Requires Auth | HTTP Method |
| ----------------------------- | ------------- | ----------- |
| `/api/v1/livechat/appearance` | `yes`         | `POST`      |

## Payload

| Argument | Example                                                                                                                                                                                                                                                                                                                                                                                              | Required | Description                                                                                                                                                                          |
| -------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `items`  | <pre class="language-json"><code class="lang-json"><strong>[
</strong>    {
       "_id":"Livechat_title",
       "value":"Hello"
    },
    {
        "_id":"Livechat_show_agent_email",
       "value":"false"
    },
    {
        "_id":"Livechat_show_agent_info",
       "value":true
    },
    {
        "_id":"Livechat_title_color",
       "value":"#b427bed"
    }

				
]
</code></pre> | Required | An array of objects containing the  `_id` and `value`  of the settings to be updated. See [appearance.md](appearance.md "mention")  example response for the `_id` of each settings. |

## Example Payload

<pre class="language-json"><code class="lang-json"><strong>[
</strong>    {
       "_id":"Livechat_title",
       "value":"Hello"
    },
    {
        "_id":"Livechat_show_agent_email",
       "value":"false"
    },
    {
        "_id":"Livechat_show_agent_info",
       "value":true
    },
    {
        "_id":"Livechat_title_color",
       "value":"#b427bed"
    }

				
]
</code></pre>

## Example Call

```bash
curl -L -X POST 'http://localhost:3000/api/v1/livechat/appearance' \
-H 'x-auth-token: qlHA60g5JQjJJG7C_8MgXoFnOiRQ8X9TWVVq4AcQeFb' \
-H 'x-user-id: rbAXPnMktTFbNpwtJ' \
-H 'Content-Type: application/json' \
-d '[
    {
       "_id":"Livechat_title",
       "value":"Hello"
    },
    {
        "_id":"Livechat_show_agent_email",
       "value":"false"
    },
    {
        "_id":"Livechat_show_agent_info",
       "value":true
    },
    {
        "_id":"Livechat_title_color",
       "value":"#b427bed"
    }

				
]'
```

## Example Result

### Success

```javascript
{
    "success": true
}
```

### Error

Any of the following errors can occur on this endpoint:

* **Id Required**: Occurs when an object in the array does not have the required property `_id`. A similar error occurs if an object in the array does not have the required property `value`.

{% tabs %}
{% tab title="Id Required" %}
```json
{
    "success": false,
    "error": "must have required property '_id' [invalid-params]",
    "errorType": "invalid-params"
}
```
{% endtab %}
{% endtabs %}

## Change Log

| Version | Description |
| ------- | ----------- |
| 6.4.0   | Added       |
