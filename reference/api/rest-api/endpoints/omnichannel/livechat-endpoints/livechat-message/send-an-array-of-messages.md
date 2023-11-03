# Send Array of Messages

Send an array of messages to a visitor.

<table><thead><tr><th width="163">HTTP Method</th><th width="295">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>POST</code></td><td><code>/api/v1/livechat/messages</code></td><td><a href="../../../authentication-endpoints/"><code>yes</code></a></td></tr></tbody></table>

## Body

<table><thead><tr><th width="163">Key</th><th width="335">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>visitor</code><mark style="color:red;"><code>*</code></mark></td><td><code>"visitor": { "token": "54fc5544030bcecda0e9"}</code></td><td>The vistor token.</td></tr><tr><td><code>messages</code><mark style="color:red;"><code>*</code></mark></td><td><code>"messages": [{"msg": "test" }, { "msg": "hello"} ]</code></td><td>The array of messages.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location 'http://localhost:3000/api/v1/livechat/messages' \
--header 'X-Auth-Token: Y97tM4GkYjgaH_fIO5dwBitQQvm3yp-AptYzGQZMX6e' \
--header 'X-User-Id: CkCPNcvsvCDfmWLqC' \
--header 'Content-Type: application/json' \
--data '{
    "visitor": {"token": "54fc5544030bcecda053311cb6b98920b"},
    "messages": [{"msg": "test" },
                { "msg": "hello"} ]
}'
```
{% endcode %}

## Example Response

```json
{
    "messages": [
        {
            "username": "guest-35",
            "msg": "test",
            "ts": "2023-10-31T08:41:29.724Z"
        },
        {
            "username": "guest-35",
            "msg": "hello",
            "ts": "2023-10-31T08:41:29.725Z"
        }
    ],
    "success": true
}
```
