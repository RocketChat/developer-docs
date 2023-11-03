# Get Available Agent Information

Get information about the currently available agent. &#x20;

<table><thead><tr><th width="165">HTTP Method</th><th width="287">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/omnichannel/agents/available</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

### Query Parameters (Optional)

Supports the [#pagination](../../../../#pagination "mention") parameters. Additional query parameters are as follows:

<table><thead><tr><th width="210">Key</th><th width="128">Data Type</th><th>Description</th></tr></thead><tbody><tr><td><code>query</code></td><td><code>string</code></td><td><p>Use the query operator to search for specific data. </p><p></p><p>For more information, see <a data-mention href="../../../../#query-and-fields">#query-and-fields</a></p></td></tr><tr><td><code>text</code></td><td><code>string</code></td><td>The response is the data that contains this text.</td></tr><tr><td><code>includeExtension</code></td><td><code>string</code></td><td><p>The voice channel extension associated with the agent. If you don't enter any extension number, the endpoint returns a list of all agents who have not been assigned any extensions.</p><p></p><p>For information about extensions, see <a href="https://docs.rocket.chat/use-rocket.chat/rocket.chat-voice-channel/voice-channel-admin-guide/configure-with-an-active-pbx-server/associate-agents-with-extensions-in-rocket.chat">Associate agents with extensions in Rocket.Chat</a>.</p></td></tr></tbody></table>

### Example Call

{% code overflow="wrap" %}
```powershell
curl --location 'http://localhost:3000/api/v1/omnichannel/agents/available' \
--header 'X-Auth-Token: Y97tM4GkYjgaH_fIO5dwBitQQvm3yp-AptYzGQZMX6e' \
--header 'X-User-Id: CkCPNcvsvCDfmWLqC' \
--data ''
```
{% endcode %}

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
