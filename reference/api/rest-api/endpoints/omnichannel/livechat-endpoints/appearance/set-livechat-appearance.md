# Set Livechat Appearance

Update the [livechat widget appearance](https://docs.rocket.chat/use-rocket.chat/omnichannel/livechat-widget-appearance) settings.

<table><thead><tr><th width="163">HTTP Method</th><th width="304">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/livechat/appearance</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `view-livechat-manager`
{% endhint %}

## Body Parameters

<table><thead><tr><th width="182.33333333333331">Key</th><th width="293">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>items</code><mark style="color:red;"><code>*</code></mark></td><td><p><code>[ { "_id":"Livechat_title", "value":"Hello" },</code> </p><p><code>{ "_id":"Livechat_show_agent_email",</code> </p><p><code>"value":"false" }</code></p><p><code>]</code></p></td><td>An array of objects containing the  <code>_id</code> and <code>value</code>  of the settings to be updated. See the  <a data-mention href="get-livechat-appearance.md">get-livechat-appearance.md</a>  example response for the <code>_id</code> of each setting.</td></tr></tbody></table>

## Example Call

```powershell
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

## Example Response

### Success

```json
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
