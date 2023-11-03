# Send New Livechat Message

Send a new livechat message to a visitor.

<table><thead><tr><th width="163">HTTP Method</th><th width="296">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/livechat/message</code></td><td><code>no</code></td></tr></tbody></table>

## Body

<table><thead><tr><th width="137">Key</th><th width="248">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>token </code><mark style="color:red;"><code>*</code></mark></td><td><code>iNKE8a6k6cjbqWhWd</code></td><td>The visitor token.</td></tr><tr><td><code>rid </code><mark style="color:red;"><code>*</code></mark></td><td><code>zRAeTszXor8CCPceB</code></td><td>The room ID.</td></tr><tr><td><code>msg </code><mark style="color:red;"><code>*</code></mark></td><td><code>Hello World!</code></td><td>The message to send to the visitor.</td></tr><tr><td><code>_id</code></td><td><code>abcdje928390</code></td><td>If you do not enter any value, a message ID is automatically generated.<br>If you want to override the message ID in the database with your own, enter a random unique string.</td></tr><tr><td><code>agent</code></td><td><p><code>agent: {</code></p><p><code>"agentId": "CkCPNcvsvCDfmWLqC",</code> </p><p><code>"username": "kim.jane" }</code></p></td><td>The <code>agent</code> parameter is an object. Enter the ID and the username of the agent.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location 'http://localhost:3000/api/v1/livechat/message' \
--header 'Content-Type: application/json' \
--data '{
    "token": "54fc5544030bcecda053311cb6b",
    "rid": "hGFwSKA28nRKut3pD",
    "msg": "Hello World!",
    "agent": {
        "agentId": "CkCPNcvsvCDfmWLqC",
        "username": "kim.jane"
    }
}'
```
{% endcode %}

## Example Response

```json
{
    "message": {
        "_id": "djsajdkscks787",
        "rid": "hGFwSKA28nRKut3pD",
        "msg": "Hello World!",
        "token": "54fc5544030bcecda053311cb6b98920bdf953f242c129d7b8065000b1f9b2e9",
        "alias": "Baek",
        "ts": "2023-10-31T13:14:29.804Z",
        "u": {
            "_id": "6523dc0ba2f73c7460e18d4d",
            "username": "guest-35",
            "name": "Baek"
        },
        "_updatedAt": "2023-10-31T13:14:29.960Z",
        "urls": [],
        "mentions": [],
        "channels": [],
        "md": [
            {
                "type": "PARAGRAPH",
                "value": [
                    {
                        "type": "PLAIN_TEXT",
                        "value": "Hello World!"
                    }
                ]
            }
        ]
    },
    "success": true
}
```
