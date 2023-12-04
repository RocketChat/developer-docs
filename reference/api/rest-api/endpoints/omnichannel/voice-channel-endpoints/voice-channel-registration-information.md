# Get Voice Channel Registration Information

Retrieves the user registration Information for the user ID.

<table><thead><tr><th width="163">HTTP Method</th><th width="337">URL</th><th>Requires Auth</th></tr></thead><tbody><tr><td><code>GET</code></td><td><code>/api/v1/connector.extension.getRegistrationInfoByUserId</code></td><td><a href="../../authentication-endpoints/">yes</a></td></tr></tbody></table>

{% hint style="info" %}
Permission required: `view-agent-extension-association`
{% endhint %}

## Query Parameters

<table><thead><tr><th width="199">Key</th><th width="206.33333333333331">Example Value</th><th>Description</th></tr></thead><tbody><tr><td><code>id</code><mark style="color:red;"><code>*</code></mark></td><td><code>ByehQjC44FwMeiLbX</code></td><td>The user ID whose registration is being retrieved.</td></tr></tbody></table>

## Example Call

{% code overflow="wrap" %}
```powershell
curl --location --request GET 'localhost:3000/api/v1/connector.extension.getRegistrationInfoByUserId'?id=CkCPNcvsvCDfmWLqC' \
--header 'X-Auth-Token: xS8jnLS2YzVy-_w8T_S0WnQm5SnADjACa7gbXmcOcLY' \
--header 'X-User-Id: 6vHSSqdBHdm2R4gfi'
```
{% endcode %}

## Example Response

```json
{
	"host": "omni-asterisk.dev.rocket.chat",
	"callServerConfig":{
		"websocketPort": "443",
		"websocketPath": "wss://omni-asterisk.dev.rocket.chat/ws"
	},
	"extensionDetails":{
		"extension": "12342",
		"password": "my$up3erP@ssw0rd",
		"authtype": "password",
		"state": "Not in use"
	}
}
```
