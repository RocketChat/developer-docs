# Get Available Agent Information

Get information about the currently available agent.

<table><thead><tr><th width="165">HTTP Method</th><th width="287">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/omnichannel/agents/available</code></td><td><code>yes</code></td></tr></tbody></table>

### Query Parameters (Optional)

Supports the [#pagination](../../../../#pagination "mention") parameters. Additional query parameters are as follows:

<table><thead><tr><th width="210">Key</th><th width="128">Data Type</th><th>Description</th></tr></thead><tbody><tr><td><code>query</code></td><td><code>string</code></td><td><p>Use the query operator to search for specific data. </p><p></p><p>For more information, see <a data-mention href="../../../../#query-and-fields">#query-and-fields</a></p></td></tr><tr><td><code>text</code></td><td><code>string</code></td><td>The response is the data that contains this text.</td></tr><tr><td><code>includeExtension</code></td><td><code>string</code></td><td><p>The voice channel extension associated with the agent.</p><p></p><p>For information about extensions, see <a href="https://docs.rocket.chat/use-rocket.chat/rocket.chat-voice-channel/voice-channel-admin-guide/configure-with-an-active-pbx-server/associate-agents-with-extensions-in-rocket.chat">Associate agents with extensions in Rocket.Chat</a>.</p></td></tr></tbody></table>

### Example Call

{% swagger method="get" path="/api/v1/omnichannel/agents/available" baseUrl="http://localhost:3000" summary="Get current available agent information" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="X-Auth-Token" required="true" %}
Auth token
{% endswagger-parameter %}

{% swagger-parameter in="header" name="X-User-Id" required="true" %}
User ID
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}

{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="" %}

{% endswagger-response %}
{% endswagger %}

### Example Response

```json
{
    "agent": {
        "_id": "XycfA5CetCPuEjqxw",
        "username": "test.agent",
        "name": "agent123",
        "status": "online",
        "statusLivechat": "online",
        "emails": [
            {
                "address": "agent123@rocket.chat",
                "verified": true
            }
        ],       
        "livechat": {
            "maxNumberSimultaneousChat": "5"
        }
    },
    "success": true
}
```
