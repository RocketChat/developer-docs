# Check Call Server Connection

Check the SIP call server connection status.

<table><thead><tr><th width="163">HTTP Method</th><th width="334">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/voip/callServer/checkConnection</code></td><td><a href="../../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `manage-voip-contact-center-settings`
{% endhint %}

## Query Parameters

<table><thead><tr><th width="219.33333333333331">Key</th><th width="232">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>websocketUrl</code><mark style="color:red;"><code>*</code></mark></td><td><code>wss://omni-asterisk.dev.rocket.chat/ws</code></td><td>The websocket URL.</td></tr><tr><td><code>host</code><mark style="color:red;"><code>*</code></mark></td><td><code>localhost</code></td><td>The hostname of the call server.</td></tr><tr><td><code>port</code><mark style="color:red;"><code>*</code></mark></td><td><code>3000</code></td><td>The port number of the websocket.</td></tr><tr><td><code>path</code><mark style="color:red;"><code>*</code></mark></td><td><code>test/voip</code></td><td>The path of the websocket.</td></tr></tbody></table>

## Example Call <a href="#example-result" id="example-result"></a>

{% code overflow="wrap" %}
```powershell
curl --location 'http://localhost:3000/api/v1/voip/callServer/checkConnection?websocketURL=wss%3A%2F%2Fomni-asterisk.dev.rocket.chat%2Fws&host=localhost&port=3000&path=test' \
--header 'X-Auth-Token: NcQtu58azANDJ1FuCmGvGVOWhYIpJVg4GqhK9h-j61l' \
--header 'X-User-Id: CkCPNcvsvCDfmWLqC'
```
{% endcode %}

## Example Response <a href="#example-result" id="example-result"></a>

```json
{
	"status": "connected" | "connection-error",
	"error?": "string"
}
```
